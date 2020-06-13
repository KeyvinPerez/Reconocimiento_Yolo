# TrainYourOwnYOLO: Creación de un detector de objetos personalizado desde cero

Este repositorio le pemitira entrenar un detector de imagen personalizado utilizando el algoritmo de visión por computadora de última generación [YOLOv3] (https://pjreddie.com/darknet/yolo/)

### Descripción general del entrenamiento

pasos para construccion del modelo:

 1. [Anotación de imagen] (/ 1_Image_Annotation /)
- Instalar la herramienta de etiquetado de objetos visuales de Microsoft (VoTT)
- identificar imagenes
 2. [Entrenamiento] (/ 2_Entrenamiento /)
 - Descargar pesas pre-entrenadas
 - Entrena tu modelo YOLO personalizado en imágenes anotadas
 3. [Inferencia] (/ 3_Inferencia /)
 - Detecta objetos en nuevas imágenes y videos

## Estructura de repositorio
+ [`1_Image_Annotation`] (/ 1_Image_Annotation /): secuencias de comandos e instrucciones para anotar imágenes
+ [`2_Training`] (/ 2_Training /): Scripts e instrucciones sobre cómo entrenar tu modelo YOLOv3
+ [`3_Inference`] (/ 3_Inference /): Scripts e instrucciones para probar su modelo de YOLO entrenado en nuevas imágenes y videos
+ [`Datos`] (/ Datos /): Datos de entrada, Datos de salida, Pesos y resultados del modelo
+ [`Utils`] (/ Utils /): scripts de utilidad utilizados por los scripts principales

#### Empezando

### Requisitos
El único requisito difícil es una versión en ejecución de python 3.6 o 3.7. Para instalar Python 3.7, vaya a
- [python.org/downloadsfont>(https://www.python.org/downloads/release/python-376/)


## instalacion opcional en la nube AWS
Para acelerar el entrenamiento, se recomienda utilizar una GPU ** con soporte CUDA **. Por ejemplo, en [AWS] (/ 2_Training / AWS /) puede usar una instancia `p2.xlarge` (GPU Tesla K80 con memoria de 12GB). La inferencia es muy rápida incluso en una CPU con aproximadamente ~ 2 imágenes por segundo.


### Instalación

#### 1a. Configuración del entorno virtual [Linux o Mac]

Clone este repositorio con:
`` `
git clone https://github.com/AntonMu/TrainYourOwnYOLO
cd TrainYourOwnYOLO /
`` `
Crear entorno virtual ** (Linux / Mac) **:
`` `
python3 -m venv env
fuente env / bin / activar
`` `
Asegúrese de que, a partir de ahora, ** ejecute todos los comandos desde su entorno virtual **.

#### 1b. Configuración del entorno virtual [Windows]
Utilice la [GUI de escritorio de Github] (https://desktop.github.com/) para clonar este repositorio en su máquina local. Navegue a la carpeta del proyecto `TrainYourOwnYOLO` y abra una ventana de Power Shell presionando ** Shift + Click derecho ** y seleccionando` Abrir ventana de PowerShell aquí` en el menú desplegable.

Crear entorno virtual ** (Windows) **:

`` `
py -m venv env
. \ env \ Scripts \ activar
`` `
! [PowerShell] (/ Utils / Screenshots / PowerShell.png)
Asegúrese de que, a partir de ahora, ** ejecute todos los comandos desde su entorno virtual **.

#### 2 Instale los paquetes requeridos [Windows, Mac o Linux]
Instale todos los paquetes necesarios con:

`` `
pip install -r required.txt
`` `
Si esto falla, es posible que primero deba actualizar su versión de pip con `pip install pip --upgrade`. Si su sistema tiene controladores CUDA en funcionamiento, usará su GPU automáticamente para capacitación e inferencia.

## Inicio rápido (solo inferencia)
Para probar el detector de cara de gato en imágenes de prueba ubicadas en [`TrainYourOwnYOLO / Data / Source_Images / Test_Images`] (/ Data / Source_Images / Test_Images) ejecute el script` Minimal_Example.py` en la carpeta raíz con:

`` `
python Minimal_Example.py
`` `

Las salidas se guardan en [`TrainYourOwnYOLO / Data / Source_Images / Test_Image_Detection_Results`] (/ Data / Source_Images / Test_Image_Detection_Results). Esto incluye:
 - Imágenes de gatos con cuadros delimitadores alrededor de las caras con puntajes de confianza y
 - [`Detection_Results.csv`] (/ Data / Source_Images / Test_Image_Detection_Results / Detection_Results.csv) archivo con nombres de archivos y ubicaciones de cuadros delimitadores.

 Si desea detectar caras de gato en sus propias imágenes, reemplace las imágenes de gato en [`Data / Source_Images / Test_Images`] (/ Data / Source_Images / Test_Images) con sus propias imágenes.

