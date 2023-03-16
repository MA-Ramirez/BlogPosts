# Guía: LaTeX en VSCode 📝💻

## Introducción
Configurar LaTeX localmente puede ser bastante doloroso para principiantes. Sin embargo, puede ser muy ventajoso a largo plazo. Por ejemplo, te permitirá escribir y editar documentos sin necesidad de conexión a internet. También, no tendrás que depender de editores online, esto quiere decir que si sus servidores están caídos no tienes que entrar en una crisis de nervios si se aproxima una fecha de entrega.

_Nota: existen muchas maneras para configurar LaTeX localmente. Aquí explico una forma que ha funcionado para mí._

## Instalación

### 1. Instalar VSCode en tu computador
Visual Studio Code (or comúnmente conocido como VSCode) es un editor de código fuente, que puedes [descargar gratis](https://code.visualstudio.com) en tu computador.

### 2. Instalar la extensión LaTeX Workshop
Ir a extensiones en VSCode e instalar LaTeX Workshop.

_Los pasos 1 y 2 te permitirán usar LaTeX en VSCode_

### 3. Instalar TeX Live
Para usar LaTeX localmente tienes que instalar TeX Live.

Dependiendo de tu sistema operativo, existen diferente opciones de descarga. Por ejemplo, si utilizas Mac OS X, puedes [descargar MacTeX](https://www.tug.org/mactex/), el cual instalará la distribución completa de TeX Live, junto con herramientas adicionales en tu computador. (No te preocupes si la página web de MacTex tiene un aspecto algo "retro". En realidad, muchas páginas y contenido relacionado a LaTeX tienen este mismo aspecto.)

_Advertencia: si descargas la distribución completa de TeX Live, por ejemplo a través de MacTeX, se descargará y se instalará un archivo de ~5GB en tu computador._

_Si te gustaría descargar una versión más pequeña de TeX Live en Mac OS X, puedes [descargar BasicTex](https://tug.org/mactex/morepackages.html), la cual tiene un tamaño de tan solo ~100MB._

Una vez instalado TeX Live, se ubicará en `/usr/local`.
Para acceder a esta carpeta a través del finder, ir a `ubicaciones -> macOS -> usr -> local`

(`cmd + shift + .` para mostrar archivos ocultos en mac.)

## Comandos útiles para usar LaTeX en VSCode ⌨️

Una vez realizados los pasos 1, 2 y 3, todo está listo para empezar a escribir documentos en LaTeX.

Los siguientes son comandos útiles para usar LaTeX en VSCode de manera más fácil:

### Construir el proyecto de LaTeX
**`cmd + alt + B`** or **`cmd + S`**

Compila el proyecto y construye en archivo pdf

###  Ver los archivos tex y pdf en paralelo
**`cmd + alt + V`**

### Ir a una ubicación específica en el archivo tex --> pdf
Ubicar el cursor en la ubicación específica del archivo tex y presionar **`cmd + alt + J`**

### Ir a una ubicación específica en el archivo pdf --> tex
**`cmd + click`** en la ubicación específica del archivo pdf

### Limpiar archivos auxiliares 
**`cmd + click + C`**

Archivos que se consideran auxiliares pueden tener las siguientes extensiones: .aux, .log, .synctex.gz, ...

### Envolver texto
**`alt + Z`**

## Manejo de errores ❗️
Errores comunes que encontrarás, especialmente si has descargado BasicTeX, son:

### Paquetes faltantes
Ejemplo del error:
```
! LaTeX Error: File 'needspace.sty' not found
```
Para solucionar este error debes descargar el paquete faltante `needspace` a través de tlmgr (el administrador de TeX Live):

* Escribir en la terminal `sudo tlmgr install <nombre-paquete>`

Usualmente, cuando utilizas el comando `sudo`, el computador te pedirá la contraseña. Esto se debe a que necesita tu autorización para realizar la operación deseada. En este caso la operación es instalar un paquete.

_Note: algunos paquetes son parte de "bundles" o colecciones, por lo tanto para instalar el paquete debes instalar el "bundle" mediante `sudo tlmgr install <nombre-bundle>`._

_Por ejemplo, para instalar el paquete `authblk` se debe instalar el bundle `preprint`._ 

Para encontrar información sobre paquetes y bundles, puedes visitar la [página web CTAN](https://www.ctan.org).


#### Comandos útiles de tlmgr 

* Para actualizar un paquete `sudo tlmgr update <nombre-paquete>`
* Para actualizar todos los paquetes `sudo tlmgr update -all`
* Para que tlmgr se actualice a sí mismo  `sudo tlmgr update -self`

[Acá](http://tug.ctan.org/info/tlmgrbasics/doc/tlmgr.pdf) puedes encontrar una guía para el uso general de tlmgr.

### Tipo de letra faltante
Ejemplo del error: 
```
! I can't find file 'phvr8t'.
<*> ...ljfour; mag:=1; ; nonstopmode; input phvr8t

```

Para solucionar este error debes descargar el tipo de letra faltante `phvr8t` a través de tlmgr (el administrador de TeX Live):

Para instalar un tipo de letra es recomendable instalar una colección de tipos de letra mediante un "bundle". 
Los siguientes son "bundles" de tipos de letra útiles:

* `sudo tlmgr install psnfss` y `sudo tlmgr install collection-fontsrecommended`

## Instalar un contador de palabras 🔢
Si te gustaría contar el número de palabras en tu documento tex al usar VSCode:

### 1. Instalar la extensión LaTeX Utilities
Ir a extensiones en VSCode e instalar LaTeX Utilities.

### 2. Instalar el paquete TeXcount
Escribir en la terminal `sudo tlmgr install texcount`

--------------------------

Para compartir preguntas o sugerencias, la creación de issues es bienvenida :)

Gracias a [Saumil Shah](https://github.com/saumil-sh) por su gran poder cerebral 👾
