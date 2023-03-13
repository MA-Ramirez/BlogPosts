# Guía práctica: cómo contribuir a proyectos de código abierto escritos en Julia 🟣💻

## Introducción
Cuando me enteré sobre el lenguaje de programación conocido como Julia, estaba muy emocionada de contribuir en proyectos de código abierto.
Sin embargo, me dí cuenta que no tenía idea (en términos prácticos) de cómo hacer esto. Al pedir consejos, me dijeron que simplemente debía crear un "PR". Como se pueden imaginar, esto es mucho más complicado de lo que suena.

Después de aprender los conceptos generales de [cómo contribuir a proyectos de código abierto](https://opensource.guide/how-to-contribute/), mi confusión continuaba. Para mí no era claro cuáles eran los pasos que llevaban a la creación de un "Pull Request".

Al investigar sobre el tema, descubrí que contribuir a proyectos de código abierto incluye pasos que son naturales y obvios para programadores con experiencia, pero que son un misterio para principiantes.
Por lo tanto, decidí escribir este blog para tratar de explicar estos pasos.

Aquí pueden encontrar una guía práctica que explica los pasos para contribuir a proyectos existentes de código abierto escritos en Julia.

## 1. Cargar el paquete en modo desarrollador

En el Julia Pkg REPL escribir: `dev <NombrePaquete>`
```julia
   _       _ _(_)_     |  Documentation: https://docs.julialang.org
  (_)     | (_) (_)    |
   _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 1.8.5 (2023-01-08)
 _/ |\__'_|_|_|\__'_|  |  Official https://julialang.org/ release
|__/                   |

(@v1.8) pkg> dev <NombrePaquete>
```

Esto permitirá que tu versión del código corra de manera independiente al paquete registrado/original.

* **Cambiar a la versión registrada** 

En el Julia Pkg REPL `add <NombrePaquete>`

`st` --> `<NombrePaquete> <version>`
  
* **Cambiar a la versión en desarrollo**
  
En el Julia Pkg REPL `dev <NombrePaquete>`
  
`st`--> `<NombrePaquete> <version> ~/.julia/dev/NombrePaquete`

_Nota: este paso permite correr la versión en desarrollo del paquete_

## 2. Crear un fork del repositorio original y conectarlo a la ruta del modo desarrollador
  
**2.1 Crear un fork del repositorio original, esto creará una copia del repo en mi propia cuenta de GitHub**

Hacer click en el botón `Fork` en la página web en GitHub del repo original.

**2.2 Ir a la carpeta (en mi computador) donde se ubica el paquete en modo desarrollador**

`~/.julia/dev/NombrePaquete`

_Tip: usar `Cmd+Shift+.` en mac para mostrar documentos escondidos (e.g. para visualizarlos en Finder)_

**2.3 Conectar mi carpeta local al fork**

Establecer `origin` y `upstream` para mi repo a través del terminal

`git remote set-url origin <mi_fork_ssh>`

`git remote add upstream <mi_fork_ssh>`

_Nota: `set-url` modifica origin/upstream ya existentes, `add` crea una nueva conexión_

## 3. Desarrollar en mi computador

**3.1 Abrir el proyecto en VSCode**

_Tip: usar `Cmd+Shift+.` en mac para mostrar documentos escondidos (e.g. para visualizarlos en Finder)_

**3.2 Abrir la consola de Julia asociada al proyecto**

`alt+J+O` in mac

**3.3 Activar Revise.jl**

Revise.jl es un paquete que carga en tiempo real el código en el que estás trabajando.
Carga automáticamente el branch en el que estás trabajando.

En el Julia REPL:

`using Revise`

`using <NombrePaquete>`

_Tip: para encontrar una función en el proyecto escribir `edit(<nombre-funcion>)`_ 

## 4. Crear una branch nueva

Crear y cambiarse a la nueva branch `git checkout -b <nombre-branch>`

Cambiarse de branch `git checkout <nombre-branch>`

Visualizar branches disponibles `git branch`
  
_Nota: siempre tener cuidado con la branch en la que estás trabajando_

## 5. Escribir tu código
Escribe el código de tu contribución

## 6. Prueba tu código
Es una buena prácticar crear tests para verificar que el nuevo código funciona correctamente

**6.1 En la carpeta test del proyecto crea un @testset con distintos @test**

**6.2 Corre los tests en el Julia Pkg REPL: `test <NombrePaquete>`**

## 7. Sube tu contribución al proyecto
Genera un push de tu contribución a tu GitHub (fork del repo original) en la branch recién creada

`git add *`

`git commit`

`git push`

## 8. Abrir un Pull Request (PR) en el repo original
Esto se realiza en la página web en GitHub del repo original. Normalmente, el botón `Compare and pull request` aparece automáticamente para realizar este proceso.

## Contribución aprobada ✅ 🎉

* Si tu contribución fue aprobada, descríbela en el [documento `changelog.md`](https://keepachangelog.com/en/1.0.0/).
Este es un documento que contiene texto, no código, con una lista ordenada de los cambios más relevantes para cada versión del proyecto.

* Si tu contribución: añade una nueva función, o cambia el nombre de una función existente, añadela al documento `api.md`

* Una vez tu contribución se ha fusionado al repo original, puedes borrar tu branch si no quieres continuar desarrollando dentro de esta

Para información práctica adicional, ver este video [video](https://www.youtube.com/watch?v=QVmU29rCjaA).

Para compartir preguntas o sugerencias, la creación de issues es bienvenida :)
