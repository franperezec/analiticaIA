# 📊 Analítica de Datos e Inteligencia Artificial

Bienvenidos al repositorio oficial del curso de **Analítica de Datos e Inteligencia Artificial** para estudiantes de ciencias sociales.

---

## 📋 Tabla de Contenidos

- [Descripción del Curso](#-descripción-del-curso)
- [Estructura del Repositorio](#-estructura-del-repositorio)
- [Configuración del Entorno](#️-configuración-del-entorno)
- [Primeros Pasos](#-primeros-pasos)
- [Recursos de Aprendizaje](#-recursos-de-aprendizaje)
- [Ejercicios Prácticos](#-ejercicios-prácticos)
- [Tecnologías](#-tecnologías)
- [Soporte](#-soporte)

---

## 📖 Descripción del Curso

Este repositorio contiene todo el material necesario para el curso de Analítica de Datos e Inteligencia Artificial, diseñado específicamente para estudiantes de ciencias sociales. Aprenderás a aplicar técnicas de machine learning, análisis causal y redes bayesianas en contextos sociales.

📋 **[Consulta el Sílabo Oficial](https://github.com/adalovelace-ec/analiticaIA/blob/main/Silabo%20Big%20Data%202025_final.pdf)** para conocer los objetivos, contenidos y evaluación del curso.

## 🗂️ Estructura General

```
├── apuntes                        # Notas y documentación del curso
├── código                         # Jupyter Notebooks con ejercicios prácticos
├── ejercicios                     # Archivos de ejercicios (Excel, datos, etc.)
├── README.md                      # Documentación principal
└── Silabo Big Data 2025_final.pdf # Programa oficial del curso
```

### 📁 **Acceso Directo a Carpetas:**
- 📚 **[Apuntes](https://github.com/adalovelace-ec/analiticaIA/tree/main/apuntes)** - Documentación teórica y guías
- 💻 **[Código](https://github.com/adalovelace-ec/analiticaIA/tree/main/c%C3%B3digo)** - Notebooks y scripts de práctica
- 🔬 **[Ejercicios](https://github.com/adalovelace-ec/analiticaIA/tree/main/ejercicios)** - Archivos de datos y ejercicios

## ⚙️ Configuración del Entorno

### 🚀 Inicio Rápido

Para configurar tu entorno de trabajo, consulta nuestra **[Guía Completa de Configuración de Entornos](https://github.com/adalovelace-ec/analiticaIA/blob/main/apuntes/configuracion-entorno.md)**.

### 📋 Opciones Disponibles

La guía incluye múltiples opciones según tus necesidades:

- **🔥 Entorno Básico** - Para la mayoría de notebooks del curso
- **🧠 Entorno Avanzado** - Para `bayes1.ipynb` y `causal_ml1.ipynb`
- **🤖 Herramientas Especializadas** - SHAP y AutoGluon (opcional)

### ⚡ Configuración Express

Si quieres empezar rápidamente con lo básico:

```bash
# Crear entorno básico
conda create -n analitica-ia python=3.12 -y
conda activate analitica-ia

# Instalar librerías esenciales
conda install numpy pandas matplotlib seaborn scikit-learn -y
conda install pytorch torchvision torchaudio cpuonly -c pytorch -y
conda install jupyter ipympl -c conda-forge -y

# Iniciar Jupyter
jupyter notebook
```

**📖 Para instrucciones completas, archivos de configuración y solución de problemas, visita la [Guía Completa](https://github.com/adalovelace-ec/analiticaIA/blob/main/apuntes/configuracion-entorno.md).**

## 🚀 Primeros Pasos

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/franperezec/analiticaIA.git
   cd analiticaIA
   ```

2. **Configurar el entorno:** Seguir la [Guía de Configuración](https://github.com/adalovelace-ec/analiticaIA/blob/main/apuntes/configuracion-entorno.md)

3. **Verificar instalación:**
   ```bash
   conda activate analitica-ia
   python -c "import pandas, numpy, matplotlib; print('✅ Entorno listo')"
   ```

4. **Abrir notebooks:**
   ```bash
   jupyter notebook
   ```

## 📚 Recursos de Aprendizaje

### 🎥 Videos Tutoriales
- **SHAP with Python (Code and Explanations)**
  - [Ver video](https://youtu.be/L8_sVRhBDLU?si=ErdEOiaB1RPw-GNs)
  - Visualizaciones SHAP (waterfall, force, beeswarm, dependence) para interpretar modelos ML

### 📖 Documentación Oficial
- **SHAP**: [Documentación completa](https://shap.readthedocs.io/en/latest/)
- **AutoGluon**: [Framework AutoML de Amazon](https://auto.gluon.ai/stable/install.html#)

### 📑 Lecturas Complementarias
- [Optimización Numérica para ML](https://www.benfrederickson.com/numerical-optimization/)
- [fmin (JavaScript)](https://github.com/benfred/fmin)

## 🔬 Ejercicios Prácticos

### 📂 **[Notebooks Principales](https://github.com/adalovelace-ec/analiticaIA/tree/main/c%C3%B3digo)**
- **`bayes1.ipynb`** - Introducción a Redes Bayesianas
- **`causal_ml1.ipynb`** - Análisis Causal con Machine Learning

### 📊 **[Archivos de Ejercicios](https://github.com/adalovelace-ec/analiticaIA/tree/main/ejercicios)**
- **Shapley 1.xlsx** - Cálculo del valor de Shapley en Excel

### 📋 Requisitos por Notebook
- **Notebooks básicos**: Entorno básico (`analitica-ia`)
- **`bayes1.ipynb` y `causal_ml1.ipynb`**: Entorno avanzado con librerías causales

**💡 Consulta la [Guía de Configuración](https://github.com/adalovelace-ec/analiticaIA/blob/main/apuntes/configuracion-entorno.md) para configurar el entorno apropiado.**

## 💻 Tecnologías

| Categoría | Herramientas |
|-----------|-------------|
| **Lenguaje** | Python 3.10+ |
| **ML/AI** | PyTorch, Scikit-learn, AutoGluon |
| **Análisis** | NumPy, Pandas, SciPy |
| **Visualización** | Matplotlib, Seaborn, Plotly |
| **Notebooks** | Jupyter Notebook, JupyterLab |
| **Entorno** | Anaconda, Miniconda |
| **Causal** | CausalML, DoWhy |
| **Interpretabilidad** | SHAP, LIME |

## 🔧 Gestión de Entornos

### 🖱️ Con Anaconda Navigator (Interfaz Gráfica)

**Crear entorno nuevo:**
- **Create** → Nombrar entorno → Seleccionar versión de Python → **Create**

**Clonar entornos:**
- Seleccionar entorno → **Clone** → Nombrar nueva copia

**Importar entorno:**
- **Import** → Seleccionar archivo `.yml` → Configurar nombre → **Import**

**Hacer backup del entorno:**
- Seleccionar entorno → **Backup** → Elegir ubicación para guardar

**Eliminar entornos:**
- Seleccionar entorno → **Remove** (ícono de papelera)

**Gestionar paquetes:**
- Dentro del entorno → **Not installed** → Buscar e instalar paquetes
- **Installed** → Ver paquetes instalados y actualizarlos
- **Updatable** → Ver y actualizar paquetes obsoletos
- Cambiar versiones específicas desde el dropdown de cada paquete

### ⌨️ Con Línea de Comandos

```bash
# Ver entornos disponibles
conda env list

# Cambiar entre entornos
conda activate nombre_entorno

# Actualizar entorno desde archivo
conda env update -f environment.yml

# Eliminar entorno
conda env remove -n nombre_entorno
```

**📖 Para más detalles sobre gestión de entornos, consulta la [Guía Completa](https://github.com/adalovelace-ec/analiticaIA/blob/main/apuntes/configuracion-entorno.md).**

## 📞 Soporte

### ❓ ¿Problemas con la instalación?
- Consulta la [Guía de Configuración](https://github.com/adalovelace-ec/analiticaIA/blob/main/apuntes/configuracion-entorno.md) para soluciones detalladas
- Verifica que Anaconda esté actualizado
- Revisa que la versión de Python sea compatible

### 🐛 ¿Encontraste un error?
- Crear un issue en este repositorio
- Incluir el mensaje de error completo
- Especificar tu sistema operativo

### 💡 ¿Sugerencias?
- Abrir un pull request con mejoras
- Contactar al profesor para dudas académicas

### 🔍 Verificación rápida del entorno:
```bash
# Activar entorno
conda activate analitica-ia

# Probar importaciones básicas
python -c "
import numpy, pandas, matplotlib, seaborn, sklearn
print('✅ Entorno básico funcionando')
"
```

---

## 👥 Equipo Docente

### 👨‍🏫 **Profesor Principal**
**Wilson Pérez**  
📧 wperez@flacso.edu.ec | wilson.amadeo.perez@gmail.com

### 👨‍💻 **Asistente de Cátedra**
**Francisco Pérez**  
📧 fperezfl@flacso.edu.ec | francisco.perezxxi@gmail.com

---

**🏫 Institución:** Facultad Latinoamericana de Ciencias Sociales (FLACSO)  
**📅 Última Actualización:** 06 de julio de 2025  
**📚 Curso:** Analítica de Datos e Inteligencia Artificial

---

*Este repositorio está en constante actualización. ¡Revisa regularmente para nuevos materiales y ejercicios!*