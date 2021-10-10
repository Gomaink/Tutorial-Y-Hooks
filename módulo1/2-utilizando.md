<h1>
    2. Utilizando.
</h1>

Primeiro de tudo, precisamos criar uma pasta onde se localizará os módulos de seu Gamemode, ele deve estar na pasta principal de seu GM e não pode conter espaços ou números, você pode optar por algo como: modulos ou modules.

<p align="center">
  <img src="/images/image4.png" width="350" title="hover text">
</p>

Após a criação da pasta, devemos criar os seus módulos, use uma extensão como .pwn/.inc/.sys.

<p align="center">
  <img src="/images/image5.png" width="350" title="hover text">
</p>

Dentro do arquivo criado, podemos começar definindo o uso da include y_hooks que será responsável pela modularização de seu Gamemode, use: 
#include <YSI-Includes\YSI_Coding\y_hooks>

<p align="center">
  <img src="/images/image6.png" width="350" title="hover text">
</p>

Após isso, você precisa vincular o módulo ao Gamemode, você pode usar:

#include "../suapastademodulos/nomedoseumodulo"

Você deve fazer isso antes da main ou no final do gamemode.

<p align="center">
  <img src="/images/image8.png" width="350" title="hover text">
</p>

IMPORTANTE: Você deve definir a include y_hooks em todos os seus módulos!