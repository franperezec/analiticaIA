# Guía Rápida: Preparando tu Entorno de Anaconda

Este instructivo te guiará para configurar tu entorno de trabajo con las librerías necesarias para los ejercicios. **Tienes dos opciones:**

## 🔥 Opción A: Crear un Nuevo Entorno (Recomendado)
## 🔧 Opción B: Usar un Entorno Existente

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

## 🔥 OPCIÓN A: Crear un Nuevo Entorno (Recomendado)

### ¿Por qué crear un nuevo entorno?
- Evita conflictos con otras instalaciones
- Mantiene organizado tu trabajo
- Fácil de eliminar si algo sale mal

### Paso A1: Crear el Entorno

Crea un entorno específico para el curso con Python 3.12:

```bash
conda create -n analitica-ia python=3.12
```

### Paso A2: Activar el Nuevo Entorno

```bash
conda activate analitica-ia
```

### Paso A3: Instalar Todas las Librerías

Instala todo lo necesario de una vez:

```bash
# Librerías básicas de data science
conda install numpy pandas matplotlib seaborn scikit-learn

# PyTorch para CPU (sin GPU)
conda install pytorch torchvision torchaudio cpuonly -c pytorch

# Jupyter y herramientas para notebooks
conda install jupyter ipympl -c conda-forge
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
conda install numpy pandas matplotlib seaborn scikit-learn
```

**Si no tienes PyTorch:**
```bash
conda install pytorch torchvision torchaudio cpuonly -c pytorch
```

**Si no tienes Jupyter o ipympl:**
```bash
conda install jupyter ipympl -c conda-forge
```

---

## 🚀 Uso Posterior

### Cómo activar tu entorno cada vez

**Si creaste un nuevo entorno (Opción A):**
```bash
conda activate analitica-ia
jupyter notebook
```

**Si usas un entorno existente (Opción B):**
```bash
conda activate base  # o tu entorno elegido
jupyter notebook
```

### Verificación Final

Independientemente de la opción elegida, verifica que todo esté instalado:

```bash
conda list
```

### Probar en Python

Abre Python y prueba que todo funcione:

```bash
python
```

Luego ejecuta:
```python
import numpy as np
import matplotlib.pyplot as plt
import torch
print("¡Todo instalado correctamente!")
exit()
```

## ✅ Librerías Requeridas

Al finalizar, deberías tener instalado:

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

---

## 🆘 Solución de Problemas

### Si algo falla:
1. **Cierra** Anaconda Prompt
2. **Abre** de nuevo como administrador
3. **Repite** los comandos

### Si los notebooks no abren:
```bash
conda install jupyter notebook
```

### Para eliminar un entorno (solo Opción A):
```bash
conda remove -n analitica-ia --all
```

---

¡Listo! Tu entorno ya está configurado con todas las herramientas necesarias para comenzar a trabajar con los notebooks.

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
# Activar tu entorno (el que creaste arriba o uno existente)
conda activate analitica-ia

# Instalar SHAP
conda install conda-forge::shap
```

### Verificar instalación:
```python
import shap
print("SHAP instalado correctamente")
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

### Instalación Modular de AutoGluon

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
```python
# Para tabular
from autogluon.tabular import TabularPredictor
print("AutoGluon Tabular instalado")

# Para series de tiempo
from autogluon.timeseries import TimeSeriesPredictor
print("AutoGluon TimeSeries instalado")

# Para multimodal
from autogluon.multimodal import MultiModalPredictor
print("AutoGluon MultiModal instalado")
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

---

## 🔄 Cambiar Entre Entornos

```bash
# Ver todos tus entornos
conda env list

# Cambiar al entorno básico
conda activate analitica-ia

# Cambiar al entorno de AutoGluon
conda activate autogluon-env

# Volver al base
conda activate base
```

---

## ⚠️ Notas Importantes

1. **SHAP** se puede instalar en tu entorno principal sin problemas
2. **AutoGluon** es mejor instalarlo en su propio entorno debido a sus muchas dependencias
3. La instalación completa de AutoGluon puede tardar 30-45 minutos
4. Si solo necesitas una funcionalidad específica, usa la instalación modular

---

¡Con estas herramientas avanzadas, podrás llevar tus proyectos de ML al siguiente nivel!