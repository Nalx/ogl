---
layout: page
status: publish
published: true
title: 'Tutorial 1 : Obrint la finestra'
date: '2011-04-07 17:54:16 +0200'
date_gmt: '2011-04-07 17:54:16 +0200'
categories: [tuto]
order: 10
tags: []
language: cat
---

# Introducció

Benvingut al primer tutorial !

Abans de saltar a OpenGL, és important primer aprendre a compilar el codi que ve amb cada tutorial, com executar-lo i el més important, com modificar el codi tu mateix.
# Prerequisits

No hi ha prerequisits per seguir aquest tutorial. Si tens experiència amb qualsevol llenguatge de programació (C, Java, Lisp, Javascript,altres) et servirà per entendre el codi, però no és necessari. Seria com aprendre dues coses al mateix temps.

Tots els tutorials són escrits en c++ "fàcil". Hem fet un gran esforç per fer el codi el més senzill possible. No hi ha plantilles, no hi ha classes i no hi ha punters. D'aquesta manera podreu entendre-ho tot malgrat que només sapigueu programar en Java.

# Oblida-ho tot

No has de saber-ho tot, però aquí has d'oblidar tot el que saps de OpenGL. Si saps quelcom que s'assembli a glBegin(), oblida-ho. Aquí aprendràs OpenGL modern (OpenGL 3 i 4), i la majoria de tutorials ensenyen OpenGL "antic" (OpenGL 1 i 2) així que oblida tot el que saps abans que el teu cervell es desfaci amb la barreja.


# Compilant els tutorials
Tots els tutorials poden ser compilats en Windows, Linux i Mac. Per a totes les plataformes el procés és pràcticament el mateix:

* **Actualitza els drivers** !! Fes-ho ! Qui avisa no és traïdor!...
* Descarrega un compilador, si no en tens cap. 
* Instal·la CMake
* Descarrega el codi font dels tutorials.
* Genera un projecte usant CMake.
* Compila el projecte.
* Juga amb els exemples!

Ara en detall per a cada plataforma. És possible que s'hagi d'adaptar el procés. Si no estàs segur, segueix les instruccions para Windows i mira d'adaptar-les.

## Generant a Windows

* Actualitzar els teus controladors hauria de ser fàcil. Tan sols has d'anar als webs de NVIDIA o AMD i descarregar els controladors. Si no saps el teu model de GPU utilitza: Panell de Control -> Sistema i seguretat -> Sistema -> Administrador de Dispositius -> Adaptadors de pantalla. Si tens una targeta gràfica integrada, els controladors normalment ja han estat instal·lats pel fabricant de l'equip (Dell, HP...)
* Sugerimos que uses Visual Studio 2015 Express de escritorio como compilador. Puedes descargarlo grátis [aquí](https://www.visualstudio.com/en-US/products/visual-studio-express-vs). Si prefieres puedes usar MinGW, en ese caso te recomendamos usar [Qt Creator](http://qt-project.org/). Instala cualquiera que desees. Los pasos a continuación son para Visual Studio, pero son los mismo para cualquier IDE.
* Descarga [CMake](http://www.cmake.org/cmake/resources/software.html) de aquí e instalelo
* [Descargue el código fuente](http://www.opengl-tutorial.org/download/) descomprímelo en una ubicación que recuerdes, por ejemplo,  C:\Users\XYZ\Projects\OpenGLTutorials\ .
* Abre CMake. En la primera línea navega hasta la carpeta descomprimida. Si no estas seguro, escoge la carpeta que contiene el archivo CMakeLists.txt . En la segunda línea  escribe la ruta del lugar donde será compilado y estarán todos los archivos. Por ejemplo puede escoger C:\Users\XYZ\Projects\OpenGLTutorials-build-Visual2015-64bits\, o C:\Users\XYZ\Projects\OpenGLTutorials\build\Visual2015-36bits\ . Nota que puede ser en cualquier lugar, no necesariamente en la misma carpeta .
![]({{site.baseurl}}/assets/images/tuto-1-window/CMake.png)

* Haz clic en el botón Configurar. Dado que es la primera vez que configuras un proyecto, CMake le preguntará el compilador que desea usar. Escoge bien dependiendo del paso 1. Si tienes windows de 64 bits, puede seleccionar 64 bits, si no lo sabes escoge 32 bits.
* Haz clic en configurar hasta que todas las líneas rojas desaparezcan. Haz clic en generar. Tu proyecto de Visual Studio project ha sido creado. En este momento puede olvidarse de CMake.
* Abre C:\Users\XYZ\Projects\OpenGLTutorials-build-Visual2010-32bits\. Verás un archivo Tutorials.sln : abralo con Visual Studio.
![]({{site.baseurl}}/assets/images/tuto-1-window/directories.png)

En el menú *Build*, haz clic en *Build All*. Cada tutorial y dependencia será generado. Cada ejecutable también será copiado en  C:\Users\XYZ\Projects\OpenGLTutorials\ . Con suerte, no habrá errores.
![]({{site.baseurl}}/assets/images/tuto-1-window/visual_2010.png)

* Abre C:\Users\XYZ\Projects\OpenGLTutorials\playground, y ejecuta playground.exe. Debe aparecer una pantalla negra.
![]({{site.baseurl}}/assets/images/tuto-1-window/empty_window.png)

Puedes ejecutar los tutoriales desde Visual Studio. Clic derecho en el proyecto Playground y "Escoger como proyecto principal". Puede depurar presionando F5.

![]({{site.baseurl}}/assets/images/tuto-1-window/StartupProject.png)

## Generant a Linux

Hay tantas variantes de Linux en el mundo que es imposible listar para cada plataforma posible. Adapta estas instrucciones si y de ser necesario consulta la documentación de tu distribución.

* Instala los controladores más recientes. Recomendamos los controladores binarios de código cerrado. No serán GNU pero de seguro si funcionan. Si tu distribución no provee los controladores automáticamente, intente con [la guía de Ubuntu](http://help.ubuntu.com/community/BinaryDriverHowto).
* Instala los compiladores necesarios, herramientas y librerías. La lista completa es : *cmake make g++ libx11-dev libxi-dev libgl1-mesa-dev libglu1-mesa-dev libxrandr-dev libxext-dev libxi-dev* . Use `sudo apt-get install *****` o `su && yum install ******`.
* [Descarga el código fuente](http://www.opengl-tutorial.org/download/) y descomprimalo, por ejemplo en ~/Projects/OpenGLTutorials/
* cd ~/Projects/OpenGLTutorials/ e ingrese los siguientes comandos :

 * mkdir build
 * cd build
 * cmake ..

* Un archivo makefile se habrá creado en el directorio build/ .
* Escribe "make all". Cada tutorial y dependencia será compilado. Cada ejecutable será copiado en ~/Projects/OpenGLTutorials/ . Con suerte, no habrá errores.
* Abra ~/Projects/OpenGLTutorials/playground, y ejecute ./playground. Debe aparecer una ventana negra.

Nota: Es recomendable usar un IDE como [Qt Creator](http://qt-project.org/). En particular este tiene soporte integrado para CMake, de manera que le proveerá una agradable experiencia para depurar. Estas son las instrucciones en QtCreator :

* En QtCreator, ve a Archivo->Herramientas->Opciones->Compilar&ejecutar->CMake
* Escribe la ruta de CMake. Probablemente sea /usr/bin/cmake
* Archivo->Abrir proyecto; Selecciona, tutorials/CMakeLists.txt
* Selecciona un directorio para construir, preferiblemente fuera del directorio de los tutoriales.
* Opcionalmente puedes usar -DCMAKE_BUILD_TYPE=Debug en los parámetros. Valide.
* Para ejecutar los tutoriales desde QtCreator, haz clic en Proyectos->Parámetros de ejecución->Directorio actual, y seleccione el directorio donde están los shaders, texturas y modelos. Ejemplo para tutorial 2 : ~/opengl-tutorial/tutorial02_red_triangle/
* haz clic en el martillo de abajo. Estos tutoriales pueden ser ejecutados desde el directorio tutorials/.


## Generant a Mac

El procedimiento es muy similar a Windows (También se puede usar Makefiles pero no los vamos a explicar aquí) :

* Instale XCode desde la App Store
* [Descargue CMake](http://www.cmake.org/cmake/resources/software.html), e instale el .dmg . No necesita instalar las herramientas de línea de comando.
* [Descargue el código fuente](http://www.opengl-tutorial.org/download/) y descomprimalo, por ejemplo en ~/Projects/OpenGLTutorials/ .
* Ejecute CMake (Applications->CMake). En la primera línea, navegue hasta el directorio descomprimido. Si no está seguro, busque el directorio que contiene el archivo CMakeLists.txt. En la segunda línea, escriba dónde se generarán todos los archivos para la compilación. Por ejemplo ~/Projects/OpenGLTutorials_bin_XCode/. Note que puede ser en cualquier parte, no necesariamente en el mismo directorio.
* Haz clic en el botón configurar. Dado que es la primera vez que configuras un proyecto, CMake te preguntará qué compilador desea usar. Escoja XCode.
* Clic en Configurar hasta que desaparezcan las líneas rojas. Clic en Generar. tu proyecto XCode ha sido creado. Ahora puedes olvidarse de CMake.
* Abre ~/Projects/OpenGLTutorials_bin_XCode/ . Verás un archivo Tutorials.xcodeproj : abrelo.
* Selecciona el tutorial que deseas ejecutar en el panel de XCode y luego usa el botón de Ejecutar para compilar y ejecutar.

![]({{site.baseurl}}/assets/images/tuto-1-window/Xcode-projectselection.png)


## Nota per a Code::Blocks

Por culpa de 2 bugs (uno en C::B y otro en CMake), debes editar la línea de comando en Proyecto->Opciones de construcción->Comandos Make, así :

![]({{site.baseurl}}/assets/images/tuto-1-window/CodeBlocksFix.png)

También debes seleccionar el directorio de trabajo tu mismo : Proyecto->Propiedades -> Proyecto a construir -> tutorial N -> directorio de trabajo ( que es : src_dir/tutorial_N/ ).

# Executant els tutorials

Debes ejecutar los tutoriales directamente de los directorios, simplemente haz doble clic en el ejecutable. Si prefieres usar la línea de comandos asegurate de hacer cd al directorio correcto.

Si quieres ejecutar los tutoriales desde el IDE, no olvides leer las instrucciones de arriba para seleccionar el directorio correcto.

# Com seguir aquests tutorials

Cada tutorial consiste en su código y sus datos, cada uno se puede encontrar en tutorialXX/. Sin embargo, nunca debes modificar estos proyectos : solo son para referencia. Abre playground/playground.cpp, y modifica este archivo en su lugar. Torturala como te plazca. Si se pierde, simplemente copia otro tutorial dentro de playground/playground.cpp, todo deberá haber vuelto a la normalidad.

Nosotros te proveemos pedacitos de código a lo largo del tutorial. No dudes en copiar y pegarlos directamente en el playground mientras va avanzando : Experimentar es bueno ! Evita leer todo el código finalizado, no vas a aprender mucho de está manera. Aun si solo copias y pegas los pedazos aprenderás más y podrás solucionar problemas.

# Obrint una finestra

Per fi! Codi OpenGL!
Be, realment no. Tots els tutorials et mostren la manera de procedir a "baix nivell", de manera que puguis veure que res passa de manera màgica. El procediment "obrir una finestra" és avorrit i no té gaire utilitat, així doncs utilitzarem GLFW, una llibreria externa per a que faci aquesta feina per nosaltres. Si realment vulguesis, podries usar l'API de Win32 de windows,l'API X11 de Linux o l'API Cocoa de Mac; o bé usar altres llibrerías "high-level" com SFML, FreeGLUT, SDL, ... Veure les pagines en els [vinculos de herramientas útiles aquí](http://www.opengl-tutorial.org/miscellaneous/useful-tools-links/) 

Dacord, som-hi! Primer, hem de lidiar amb les dependencies : necesitem el més bàsic per a mostrar missatges per consola :

``` cpp
// Incloem les capçaleres standard
#include <stdio.h>
#include <stdlib.h>
```

Primer de tot, GLEW. Això de fet sí que és un xic màgic, però ho explicarem més endavant.

``` cpp
// Incloem GLEW. Cal incloure sempre avans de gl.h i glfw.h, un xic màgic també.
#include <GL/glew.h>
```

Hem decidit deixar que GLFW gestioni la finestra i el teclat, així doncs l'incloem :

``` cpp
// Incloem GLFW
#include <GL/glfw3.h>

```

En realidad no necesitamos ésta en este momento, pero una librería para matemáticas 3D. Nos será muy útil pronto. No hay magia en GLM, puedes escribir la tuya propia si deseas. Simplemente está es útil. El "using namespace" está allí para evitar que debamos escribir "glm::vec3", y escribamos "vec3" en su lugar.

``` cpp
// Incloem GLM
#include <glm/glm.hpp>
using namespace glm;
```

Si no puedes copiar el código, todo esto está incluído en playground.cpp. 
El compilador se va a quejar porque no hay una función main(). Creamos una :

``` cpp
int main(){
```

Lo primero que haremos es inicializar GLFW :

``` cpp
// Inicializar GLFW
if( !glfwInit() )
{
    fprintf( stderr, "Error al inicializar GLFW\n" );
    return -1;
}
```

Ahora podemos crear nuestra primera ventana OpenGL !

 

``` cpp
glfwWindowHint(GLFW_SAMPLES, 4); // 4x antialiasing
glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3); // Queremos OpenGL 3.3
glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
glfwWindowHint(GLFW_OPENGL_FORWARD_COMPAT, GL_TRUE); // Para hacer feliz a MacOS ; Aunque no debería ser necesaria
glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE); //No queremos el viejo OpenGL 

//Crear una ventana y su contexto OpenGL
GLFWwindow* window; // (En el código que viene aqui, está variable es global)
window = glfwCreateWindow( 1024, 768, "Tutorial 01", NULL, NULL);
if( window == NULL ){
    fprintf( stderr, "Falla al abrir una ventana GLFW. Si usted tiene una GPU Intel, está no es compatible con 3.3. Intente con la versión 2.1 de los tutoriales.\n" );
    glfwTerminate();
    return -1;
}
glfwMakeContextCurrent(window); // Inicializar GLEW
glewExperimental=true; // Se necesita en el perfil de base.
if (glewInit() != GLEW_OK) {
    fprintf(stderr, "Falló al inicializar GLEW\n");
    return -1;
}
```

Construye este y ejecutalo. Una ventana debe aparecer y se cerrará de inmediato. Debemos hacer que espere hasta que alguien oprima la tecla ESC :

``` cpp
// Capturar la tecla ESC cuando sea presionada
glfwSetInputMode(window, GLFW_STICKY_KEYS, GL_TRUE);

do{
    // No vamos a pintar nada, nos vemos en el tutorial 2 !

    // Intercambiar buffers
    glfwSwapBuffers(window);
    glfwPollEvents();

} // Revisar que la tecla ESC fue presionada y cerrar la ventana
while( glfwGetKey(window, GLFW_KEY_ESCAPE ) != GLFW_PRESS &&
glfwWindowShouldClose(window) == 0 );
```

I així finalitza el primer tutorial ! En el tutorial 2 aprendràs a dibuixar un triangle.
