# Guía Rápida: Preparando tu Entorno de Anaconda

Este instructivo te guiará para verificar tu entorno de trabajo, tu versión de Python y para instalar las librerías necesarias para los ejercicios.

## Paso 1: Abrir Anaconda Prompt

Busca **"Anaconda Prompt"** en el menú de inicio de tu computadora y ábrelo. Verás una terminal o ventana de comandos.

## Paso 2: Ver tus Entornos

Para ver la lista de todos los entornos de Conda que tienes, escribe el siguiente comando y presiona `Enter`:

```bash
conda env list
```

Verás una lista de tus entornos. El que está activo tendrá un asterisco (`*`) al lado. Generalmente, trabajarás en el entorno `base` a menos que hayas creado uno nuevo.

## Paso 3: Activar tu Entorno de Trabajo

Si el entorno que quieres usar no está activo, actívalo con el siguiente comando. Reemplaza `<nombre_del_entorno>` con el nombre de tu entorno (por ejemplo, `base`).

```bash
conda activate <nombre_del_entorno>
```

## Paso 4: Comprobar la Versión de Python

Ahora que tu entorno está activo, comprueba tu versión de Python. Los notebooks fueron creados con la versión 3.12.9, que viene en el entorno de Anaconda, pero cualquier versión moderna de Python 3 (3.8 en adelante) debería funcionar.

```bash
python --version
```

Asegúrate de que la versión que aparece es una versión de Python 3.

## Paso 5: Revisar Paquetes Instalados

Vamos a verificar si ya tienes `numpy` y `matplotlib`, que son muy comunes y suelen venir preinstalados. Ejecuta el siguiente comando para ver la lista completa de paquetes:

```bash
conda list
```

Puedes buscar en la lista o usar este comando para filtrar directamente:

```bash
conda list numpy
conda list matplotlib
```

Si estos comandos te muestran los paquetes, ya están instalados. Si no, no te preocupes, los instalaremos en el siguiente paso.

## Paso 6: Instalar las Librerías Faltantes

Ahora, instala las librerías que necesitas para los ejercicios de redes neuronales.

### 1. Instalar PyTorch (versión para CPU)

El archivo `tensores1.ipynb` indica usar una versión de PyTorch que no requiere una tarjeta de video NVIDIA (GPU). Copia y pega el siguiente comando completo:

```bash
conda install pytorch torchvision torchaudio cpuonly -c pytorch
```

### 2. Instalar NumPy y Matplotlib (si faltaban)

Si en el paso 5 descubriste que no los tenías, instálalos con:

```bash
conda install numpy matplotlib
```

### 3. Instalar `ipympl` para Gráficos Interactivos

Esta librería es útil para las visualizaciones en los notebooks.

```bash
conda install -c conda-forge ipympl
```

## Paso 7: Verificación Final

Una vez terminadas las instalaciones, puedes volver a ejecutar `conda list` para confirmar que `pytorch`, `torchvision` y `ipympl` aparecen ahora en tu lista de paquetes.

```bash
conda list
```

## ✅ Librerías Requeridas

Al finalizar, deberías tener instalado:

- **Python 3.8+, recomendado 3.12.9 que viene en Anaconda**
- **PyTorch** (versión CPU)
- **TorchVision** 
- **TorchAudio**
- **NumPy**
- **Matplotlib**
- **ipympl**

---

¡Listo! Tu entorno ya está configurado con todas las herramientas necesarias para comenzar a trabajar con los notebooks.