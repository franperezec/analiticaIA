# Guía Completa: Configuración de Entornos de Anaconda

Este instructivo te guiará para configurar tu entorno de trabajo con las librerías necesarias para todos los ejercicios del curso. **Tienes múltiples opciones según tus necesidades:**

## 🎯 Opciones de Configuración

- **🔥 Opción A:** Crear un Nuevo Entorno Básico (Recomendado para principiantes)
- **🔧 Opción B:** Usar un Entorno Existente
- **🧠 Opción C:** Entorno para Redes Bayesianas y Análisis Causal
- **🚀 Sección Avanzada:** SHAP y AutoGluon

---

## Preparación Inicial

### Paso 1: Abrir Anaconda Prompt

Busca **"Anaconda Prompt"** en el menú de inicio de tu computadora y ábrelo. Verás una terminal o ventana de comandos.

### Paso 2: Ver tus Entornos Actuales

Para ver la lista de todos los entornos de Conda que tienes:

```bash
conda env list
```

Verás una lista de tus entornos. El que está activo tendrá un asterisco (`*`) al lado.

---

## 🔥 OPCIÓN A: Crear un Nuevo Entorno Básico (Recomendado)

### ¿Por qué crear un nuevo entorno?
- Evita conflictos con otras instalaciones
- Mantiene organizado tu trabajo
- Fácil de eliminar si algo sale mal

### Paso A1: Crear el Entorno

Crea un entorno específico para el curso con Python 3.12:

```bash
conda create -n analitica-ia python=3.12 -y
```

### Paso A2: Activar el Nuevo Entorno

```bash
conda activate analitica-ia
```

### Paso A3: Instalar Todas las Librerías

Instala todo lo necesario de una vez:

```bash
# Librerías básicas de data science
conda install numpy pandas matplotlib seaborn scikit-learn -y

# PyTorch para CPU (sin GPU)
conda install pytorch torchvision torchaudio cpuonly -c pytorch -y

# Jupyter y herramientas para notebooks
conda install jupyter ipympl -c conda-forge -y
```

### Paso A4: Verificación

```bash
conda list
python --version
```

---

## 🔧 OPCIÓN B: Usar un Entorno Existente

### Paso B1: Activar tu Entorno

Activa el entorno que quieres usar (generalmente `base`):

```bash
conda activate base
# O si tienes otro entorno:
# conda activate <nombre_del_entorno>
```

### Paso B2: Verificar Python

Comprueba que tienes Python 3.8 o superior:

```bash
python --version
```

### Paso B3: Revisar Librerías Existentes

Verifica qué librerías ya tienes instaladas:

```bash
conda list numpy
conda list matplotlib
conda list pytorch
```

### Paso B4: Instalar Librerías Faltantes

Instala solo lo que te falte:

**Si no tienes las librerías básicas:**
```bash
conda install numpy pandas matplotlib seaborn scikit-learn -y
```

**Si no tienes PyTorch:**
```bash
conda install pytorch torchvision torchaudio cpuonly -c pytorch -y
```

**Si no tienes Jupyter o ipympl:**
```bash
conda install jupyter ipympl -c conda-forge -y
```

---

## 🧠 OPCIÓN C: Entorno para Redes Bayesianas y Análisis Causal

### ¿Cuándo usar esta opción?
- Cuando trabajarás con los notebooks `bayes1.ipynb` y `causal_ml1.ipynb`
- Necesitas librerías especializadas para inferencia causal
- Quieres las herramientas más avanzadas del curso

### 📋 Archivos necesarios para esta opción:
- `environment.yml` - Configuración completa del entorno
- `requirements.txt` - Lista de paquetes pip

### C1: Usando environment.yml (Método más rápido)

```bash
# Navegar al directorio del proyecto
cd "ruta/a/tu/proyecto/analiticaIA"

# Crear entorno desde archivo
conda env create -f environment.yml

# Activar entorno
conda activate causal_ml

# Librerías gráficos causales
pip install git+https://github.com/py-why/causal-learn.git

# Verificar instalación
conda list
```

### C2: Usando requirements.txt (Más control)

```bash
# Crear nuevo entorno
conda create -n causal_req python=3.13 -y

# Activar entorno
conda activate causal_req

# Instalar dependencias de sistema (IMPORTANTE para gráficos)
conda install -c conda-forge graphviz pygraphviz -y
pip install git+https://github.com/py-why/causal-learn.git

# Navegar al proyecto e instalar paquetes
cd "ruta/a/tu/proyecto/analiticaIA"
pip install -r requirements.txt

# Registrar kernel para Jupyter
python -m ipykernel install --user --name causal_req
```

### C3: Instalación manual paso a paso

```bash
# Crear entorno específico
conda create -n causal_manual python=3.12 -y

# Activar entorno
conda activate causal_manual

# Instalar librerías básicas
conda install numpy pandas matplotlib seaborn scikit-learn -y

# PyTorch
conda install pytorch torchvision torchaudio cpuonly -c pytorch -y

# Jupyter y herramientas
conda install jupyter ipympl -c conda-forge -y

# Dependencias para gráficos de redes (CRÍTICO para Bayes)
conda install -c conda-forge graphviz pygraphviz -y

# Librerías especializadas para análisis causal
pip install causalnex dowhy causalml pgmpy

# Librerías adicionales para redes bayesianas
pip install networkx pyvis bnlearn

# Verificar instalación
python -c "import causalnex, dowhy, causalml, pgmpy; print('✅ Librerías causales instaladas')"
```

### C4: Configuración en Anaconda Navigator

1. **Crear entorno:**
   - **Environments** → **Create** → Nombre: `causal_ml` → Python 3.12
2. **Instalar paquetes básicos:**
   - Buscar e instalar: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`
3. **Instalar PyTorch:**
   - Buscar `pytorch` → Seleccionar canal `pytorch` → Instalar
4. **Instalar Jupyter:**
   - Buscar `jupyter` → Instalar
5. **Instalar graphviz:**
   - Cambiar canal a `conda-forge` → Buscar `graphviz` y `pygraphviz` → Instalar

---

## 🚀 Uso Posterior

### Cómo activar tu entorno cada vez

**Para entorno básico (Opción A):**
```bash
conda activate analitica-ia
jupyter notebook
```

**Para entorno existente (Opción B):**
```bash
conda activate base  # o tu entorno elegido
jupyter notebook
```

**Para entorno causal (Opción C):**
```bash
conda activate causal_ml
jupyter notebook
```

### Verificación Final para Cualquier Opción

```bash
# Ver entorno activo
conda info --envs

# Listar paquetes instalados
conda list

# Probar importaciones básicas
python -c "
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import sklearn
print('📊 Librerías básicas: ✅')
"
```

### Probar Librerías Causales (Solo Opción C)

```bash
python -c "
try:
    import causalnex
    import dowhy
    import causalml
    import pgmpy
    print('🧠 Librerías causales: ✅')
except ImportError as e:
    print(f'❌ Error: {e}')
"
```

## ✅ Librerías Requeridas por Opción

### **Todas las opciones incluyen:**
- **Python 3.8+** (recomendado 3.12)
- **NumPy** - Cálculos numéricos
- **Pandas** - Manipulación de datos
- **Matplotlib** - Gráficos básicos
- **Seaborn** - Gráficos estadísticos
- **PyTorch** - Redes neuronales (versión CPU)
- **TorchVision** - Visión computacional
- **TorchAudio** - Procesamiento de audio
- **Scikit-learn** - Machine learning
- **Jupyter** - Notebooks interactivos
- **ipympl** - Gráficos interactivos en notebooks

### **Opción C (Causal) incluye además:**
- **GraphViz** - Visualización de gráficos
- **PyGraphViz** - Interface Python para GraphViz
- **CausalNex** - Redes bayesianas y análisis causal
- **DoWhy** - Framework de inferencia causal
- **CausalML** - Machine learning causal
- **pgmpy** - Modelos gráficos probabilísticos
- **NetworkX** - Análisis de redes
- **bnlearn** - Aprendizaje de redes bayesianas

---

## 🆘 Solución de Problemas

### Problemas Generales

**Si algo falla:**
1. **Cierra** Anaconda Prompt
2. **Abre** de nuevo como administrador
3. **Repite** los comandos

**Si los notebooks no abren:**
```bash
conda install jupyter notebook -y
```

**Para eliminar un entorno problemático:**
```bash
conda env remove -n nombre_entorno
```

### Problemas Específicos de Librerías Causales

**Error con GraphViz en Windows:**
```bash
# Instalar desde conda-forge
conda install -c conda-forge graphviz pygraphviz -y

# Si persiste el error, instalar GraphViz manualmente:
# Descargar desde: https://graphviz.org/download/
# Agregar a PATH: C:\Program Files\Graphviz\bin
```

**Error con pygraphviz en Mac:**
```bash
# Instalar dependencias del sistema
brew install graphviz

# Reinstalar pygraphviz
pip uninstall pygraphviz
pip install pygraphviz
```

**Error "No module named 'causalnex'":**
```bash
# Verificar entorno activo
conda info --envs

# Reinstalar en el entorno correcto
conda activate causal_ml
pip install causalnex dowhy causalml pgmpy
```

---

# 🚀 SECCIÓN AVANZADA: Herramientas de ML Especializadas

Esta sección es **opcional** y está dirigida a usuarios que necesiten herramientas más avanzadas para:
- **SHAP**: Explicar e interpretar modelos de Machine Learning
- **AutoGluon**: Automatizar completamente el proceso de ML

## 📊 SHAP - Interpretabilidad de Modelos

**¿Qué es SHAP?** Herramienta para entender cómo tus modelos toman decisiones.

**Documentación oficial:** https://anaconda.org/conda-forge/shap

### Instalación de SHAP

```bash
# Activar tu entorno (cualquiera de las opciones A, B o C)
conda activate analitica-ia  # o causal_ml

# Instalar SHAP
conda install conda-forge::shap -y
```

### Verificar instalación:
```bash
python -c "import shap; print('SHAP instalado correctamente')"
```

---

## 🤖 AutoGluon - Machine Learning Automatizado

**¿Qué es AutoGluon?** Automatiza la creación, entrenamiento y optimización de modelos de ML.

**Documentación oficial:** https://auto.gluon.ai/

### Crear un Entorno Específico para AutoGluon

AutoGluon funciona mejor con Python 3.11 y su propio entorno:

```bash
# Crear entorno específico para AutoGluon
conda create -n autogluon-env python=3.11 -y
conda activate autogluon-env
```

### Instalación para Windows (CPU)

**Requisito:** Git instalado (https://git-scm.com/download/win)

```bash
# Instalar dependencias
pip install uv
python -m uv pip install -U torch torchvision --extra-index-url https://download.pytorch.org/whl/cpu

# Clonar e instalar AutoGluon completo
git clone https://github.com/autogluon/autogluon
cd autogluon && ./full_install.sh
```

### Instalación para Mac (CPU)

```bash
# Configurar libomp (importante para LightGBM)
brew uninstall -f libomp
wget https://raw.githubusercontent.com/Homebrew/homebrew-core/fb8323f2b170bd4ae97e1bac9bf3e2983af3fdb0/Formula/libomp.rb
brew install libomp.rb
rm libomp.rb

# Preparar herramientas
pip install -U pip
pip install -U setuptools wheel

# Clonar e instalar AutoGluon
git clone https://github.com/autogluon/autogluon
cd autogluon && ./full_install.sh
```

### Instalación Modular de AutoGluon (Recomendado)

Si no necesitas todas las funcionalidades, puedes instalar solo lo que necesites:

#### 📊 Para Datos Tabulares (CSV, Excel, etc.)
```bash
# Instalación completa para tabular
pip install autogluon.tabular[all]

# O solo con modelos específicos
pip install autogluon.tabular[lightgbm,catboost]
```

#### 📈 Para Series de Tiempo
```bash
pip install autogluon.timeseries
```

#### 🖼️ Para Imágenes y Texto (Multimodal)
```bash
pip install autogluon.multimodal

# Para detección de objetos (opcional)
mim install "mmcv==2.1.0"
pip install "mmdet==3.2.0"
pip install pycocotools  # En Windows: pip install pycocotools-windows
```

#### 🔧 Opciones Adicionales

**Para modelos más rápidos (KNN 25x más rápido):**
```bash
pip install autogluon.tabular[all,skex]
```

**Para modelos interpretables:**
```bash
pip install autogluon.tabular[all,imodels]
```

**Para exportar modelos a ONNX:**
```bash
pip install autogluon.tabular[all,skl2onnx]
```

### Verificar instalación de AutoGluon:
```bash
python -c "
# Para tabular
from autogluon.tabular import TabularPredictor
print('AutoGluon Tabular: ✅')

# Para series de tiempo
try:
    from autogluon.timeseries import TimeSeriesPredictor
    print('AutoGluon TimeSeries: ✅')
except ImportError:
    print('AutoGluon TimeSeries: ❌ (no instalado)')

# Para multimodal
try:
    from autogluon.multimodal import MultiModalPredictor
    print('AutoGluon MultiModal: ✅')
except ImportError:
    print('AutoGluon MultiModal: ❌ (no instalado)')
"
```

---

## 💡 Cuándo Usar Cada Herramienta

### Usa SHAP cuando:
- Necesites explicar las predicciones de tu modelo
- Quieras identificar qué variables son más importantes
- Debas justificar decisiones del modelo ante stakeholders

### Usa AutoGluon cuando:
- Tengas datos tabulares y quieras el mejor modelo automáticamente
- No tengas experiencia en ML pero necesites buenos resultados
- Quieras comparar múltiples modelos rápidamente
- Trabajes con series de tiempo o datos multimodales

### Usa las Librerías Causales cuando:
- Necesites inferir relaciones causa-efecto en tus datos
- Trabajes con redes bayesianas
- Quieras estimar efectos de tratamientos o intervenciones
- Analices datos observacionales donde la correlación no implica causalidad

---

## 🔄 Gestión Completa de Entornos

### Ver todos tus entornos:
```bash
conda env list
```

### Cambiar entre entornos:
```bash
# Entorno básico
conda activate analitica-ia

# Entorno causal
conda activate causal_ml

# Entorno AutoGluon
conda activate autogluon-env

# Volver al base
conda activate base
```

### Eliminar entornos:
```bash
# Eliminar entorno específico
conda env remove -n nombre_entorno

# Confirmar eliminación
conda env list
```

### Exportar entornos para compartir:
```bash
# Activar entorno que quieres exportar
conda activate causal_ml

# Exportar configuración completa
conda env export > entorno_causal.yml

# Exportar solo paquetes principales
conda env export --no-builds > entorno_causal_limpio.yml
```

### Clonar entornos:
```bash
# Clonar entorno existente
conda create --name nuevo_entorno --clone entorno_existente
```

---

## ⚠️ Notas Importantes

1. **SHAP** se puede instalar en cualquier entorno sin problemas
2. **AutoGluon** es mejor instalarlo en su propio entorno debido a sus muchas dependencias
3. **Librerías causales** requieren GraphViz para visualizaciones - asegúrate de instalarlo
4. La instalación completa de AutoGluon puede tardar 30-45 minutos
5. Si solo necesitas una funcionalidad específica, usa la instalación modular
6. Los entornos consumen espacio en disco - elimina los que no uses

---

## 🎯 Recomendaciones Finales

### Para principiantes:
- Empieza con **Opción A** (entorno básico)
- Agrega SHAP cuando necesites interpretabilidad
- Considera la **Opción C** solo cuando trabajes con análisis causal

### Para usuarios avanzados:
- Usa **Opción C** si trabajas con causalidad desde el inicio
- Crea entornos específicos para proyectos diferentes
- Mantén un entorno base limpio para experimentación

### Para el curso:
- **Notebooks básicos**: Cualquier opción (A o B)
- **bayes1.ipynb y causal_ml1.ipynb**: Requieren Opción C
- **Proyectos avanzados**: Considera AutoGluon

---

¡Con esta guía completa, tendrás todas las herramientas necesarias para aprovechar al máximo el curso de Analítica de Datos e IA!