# Manual de Usuario

## Introduccion

En esta sección se detallan los pasos a seguir para el uso adecuado del
software Detector de Pivotes de Riego y Silobolsas en Imágenes
Satelitales para aplicaciones agrícolas.

## Pre-requisitos

Contar con Docker instalado en la computadora.

En el caso de no optar por el uso de Docker, se puede correr localmente
de contar con los siguientes requerimientos:

- Distribución Linux: Debian o Ubuntu preferentemente (o sus
  derivados).

- Python 3.7 o superior.

- Virtualenv

## Instalación

1.  Descargar o clonar el repositorio desde Github:
    <https://github.com/gianfrancob/detector_pivotes_silobolsas>

2.  Inicializar el contenedor Docker corriendo: _docker run
    ./utils/docker/Dockerfile_

3.  En el caso de no optar por el uso de Docker, se puede correr
    localmente de la siguiente manera:

    - Crear entorno virtual usando virtualenv: _virtualenv venv_

    - Activar el entorno: _source ./venv/bin/activate_

    - Instalar las dependencias en el entorno: _pip install -r
      ./requirements.txt_

4.  Iniciar el servicio backend: _python
    ./utils/flask_rest_api/restapi_pivot_silobolsa.py --port 5000_

5.  Ingresar a la pagina abriendo en el navegador el siguiente fichero
    HTML: _./utils/boostrap_frontend/index.html_

## Ingresar a la pagina

Para ejecución local, la dirección URL donde se encuentra la aplicación
es: _DIRECTORIO RAIZ/utils/boostrap_frontend/index.html_

Para ejecución web, dependerá particularmente del tipo de despliegue
implementado.

## Cargar una imagen

Una vez en la pagina principal, dirigirse al botón \"Seleccionar
archivo\" que se encuentra en la mitad de la misma y hacer clic en él
para seleccionar una imagen o desde la computadora del usuario, los
formatos soportados son .jpg, .png .

### Error en el formato de la imagen

Si el formato de la imagen cargada esta dañado o es invalido, se
mostrara en un mensaje

## Cargar varias imágenes

Para la opción del análisis de un conjunto de imágenes, previamente se
debe crear un archivo de compresión con todas las imágenes en alguno de
los siguientes formatos: RPM (.rpm), RAR (.rar), RZIP (.rz), TAR (.tar),
XZ (.xz), ZIP (.zip, .jar), GZIP (.gz), 7z (.7z).

Luego, hacer clic en el botón \"Seleccionar archivo\" para subir el
archivo con todas las imágenes a ser analizadas.

**Nota**: No debe salir ningún mensaje de error para continuar con el
análisis.

## Inicio de la detección

Una vez cargada la imagen o las imágenes en formatos validos, hacer clic
en el botón \"Submit\", para dar inicio a la detección.

El botón cambiara de nombre y aparece como \"Loading\" como indicio de q
la detección esta en proceso.

## Descarga de imágenes

Una vez realizada la detección de los objetos, se va a mostrar como
resultado las imágenes analizadas indicando la presencia de los objetos
Silo bolsas o Riegos por Pívot junto con una tabla donde se detalla la
información de la detección.

## Agradecimientos

El siguiente proyecto no hubiera sido posible sin el gran trabajo
realizado por Ultralytics que desarrolló el modelo de YOLOv5 en
Pytorch: <https://github.com/ultralytics/yolov5>.
