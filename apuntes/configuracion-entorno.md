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