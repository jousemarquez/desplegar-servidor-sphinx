# desplegar-servidor-sphinx
Desplegar servidor Sphinx para crear una web dinámica con el contenido autogenerado por Sphinx

## Instalación de Sphinx

Para comenzar con Sphinx, sigue estos pasos sencillos:

1. Instala Sphinx utilizando el siguiente comando:

```
pip3 install -U Sphinx
```

2. Crea un directorio para tu proyecto, por ejemplo, en /home/azureuser:
```
mkdir sphinx-project
cd sphinx-project
```

3. Inicia Sphinx con el asistente rápido:

```
sphinx-quickstart
```

Nota:
Responde "no" a la primera pregunta sobre la estructura de carpetas.
Rellena los datos según tus preferencias. Para el nombre del proyecto, indica "español (es)".

4. Abre el archivo conf.py y añade el siguiente código:

```
import os 
import sys 
sys.path.insert(0, os.path.abspath('.'))
```

5. Crea un directorio llamado "docs":

```
mkdir docs
cd docs
```

6. Dentro de la carpeta "docs", crea un archivo llamado "first_doc.rst" utilizando tu editor preferido (Si no es VIM, golpe de remo):

```
vim first_doc.rst
```

7. Dentro de este archivo, se escribe la documentación utilizando el formato ReStructuredText (he utilizad el README.md del repositorio https://github.com/jousemarquez/instalacion-apache-tomcat/tree/master)
Guardar el archivo.

8. Regresar al directorio del proyecto Sphinx y ejecuta el siguiente comando para generar la documentación en formato HTML:

```
make html
```

## Despliegue

Existen dos alternativas para visualizar la documentación generada:

1. Abre el archivo "index.html" en la carpeta "html" localmente.
2. Utiliza Apache para desplegar la web generada por Sphinx. Copia el contenido de la carpeta "html" en la carpeta de despliegue de Apache. Si ya tienes un puerto configurado, simplemente utiliza el siguiente comando:

```
cp -r /home/azureuser/sphinx-project/build/html/* .
```
Esto copiará el contenido de la carpeta "html" a la carpeta que sirve la web en tu servidor Apache

## Reflexiones sobre Sphinx

### Valoración de Sphinx y Alternativas

Sphinx ofrece potentes capacidades de documentación, especialmente en proyectos extensos. Su estructura formal es beneficiosa para colaboraciones complejas. Sin embargo, en proyectos más simples, opciones más directas como Markdown pueden ser suficientes.

### Crítica sobre Procesos de Documentación

La falta de documentación inicial dificulta la integración y puede generar errores. Documentación clara facilita la comprensión, valoración del trabajo y transmisión de conocimientos entre compañeros, siendo crucial para el éxito del proyecto.
