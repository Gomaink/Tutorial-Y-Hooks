<h1>
    2. Utilizando.
</h1>

En primer lugar, necesitamos crear una carpeta donde se ubicarán los módulos del gamemode, debe estar en la carpeta principal de tu GM y no puede contener espacios ni números, puedes elegir algo como: "modulos" o "modules". 

<p align="center">
  <img src="/images/image4.png" width="350" title="hover text">
</p>

Después de crear la carpeta, debemos crear sus módulos, use una extensión como .pwn, .inc o .sys.

<p align="center">
  <img src="/images/image5.png" width="350" title="hover text">
</p>

Dentro del archivo creado, podemos comenzar por definir el uso de la librería y_hooks que será responsable de la modularización de tu gamemode, usa: #include <YSI-Include\YSI_Coding\y_hooks> 

<p align="center">
  <img src="/images/image6.png" width="350" title="hover text">
</p>

Después de eso, debe incluir el módulo al gamemode, puede usar:

#include "../carpeta de los módulos/nombre del módulo"

Debes hacer esto antes del script principal o al final del script. 

<p align="center">
  <img src="/images/image8.png" width="350" title="hover text">
</p>

IMPORTANTE: ¡Debes incluir y_hooks en todos tus módulos! 