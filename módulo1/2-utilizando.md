<h1>
    2. Utilizando.
</h1>

En primer lugar, necesitamos crear una carpeta donde se ubicar�n los m�dulos del gamemode, debe estar en la carpeta principal de tu GM y no puede contener espacios ni n�meros, puedes elegir algo como: "modulos" o "modules". 

<p align="center">
  <img src="/images/image4.png" width="350" title="hover text">
</p>

Despu�s de crear la carpeta, debemos crear sus m�dulos, use una extensi�n como .pwn, .inc o .sys.

<p align="center">
  <img src="/images/image5.png" width="350" title="hover text">
</p>

Dentro del archivo creado, podemos comenzar por definir el uso de la librer�a y_hooks que ser� responsable de la modularizaci�n de tu gamemode, usa: #include <YSI-Include\YSI_Coding\y_hooks> 

<p align="center">
  <img src="/images/image6.png" width="350" title="hover text">
</p>

Despu�s de eso, debe incluir el m�dulo al gamemode, puede usar:

#include "../carpeta de los m�dulos/nombre del m�dulo"

Debes hacer esto antes del script principal o al final del script. 

<p align="center">
  <img src="/images/image8.png" width="350" title="hover text">
</p>

IMPORTANTE: �Debes incluir y_hooks en todos tus m�dulos! 