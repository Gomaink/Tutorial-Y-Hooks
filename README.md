# Tutorial-Y-Hooks
> Um breve tutorial sobre a utilização da include y_hooks para a modularização de sistemas no SA-MP.

<br>

1. [Instalação](#-Instalação)

2. [Utilização](#-Utilização)

3. [Callbacks](#-Callbacks)

3. [Útil](#-Útil)
   
<br>

## 🚀 Instalação

Na instalação é onde muitos se perdem, porém é algo muito simples de ser feito.

Acesse o GitHub do Y_Less e baixe a biblioteca YSI.

Link do GitHub: https://github.com/pawn-lang/YSI-Includes<br>
Link para download direto: https://www.mediafire.com/file/koiqd2q9m2thelf/YSI-Includes.zip/file

Se optou em baixar pelo GitHub, clique em Code e depois em Download Zip como na imagem.

<p align="center">
  <img src="/images/image2.png" width="350" title="hover text">
</p>

Caso contrário e você tenha optado pelo mediafire, apenas clique no botão download como na imagem.

<p align="center">
  <img src="/images/image1.png" width="350" title="hover text">
</p>

Após a instalação, extraia o arquivo após isso irá lhe dar uma pasta com o nome "YSI-Includes" ou algo parecido.

<p align="center">
  <img src="/images/image3.png" width="350" title="hover text">
</p>

Clique sobre a pasta, pressione o botão direito do mouse e clique em copiar, após isso vá até a pasta de seu gamemode e cole em pawno/includes.

## ☕ Utilização

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

## 📞 Callbacks

Para a utilização de callbacks em módulos é bem simples, você deve apenas trocar o nome "public" por "hook" em seu módulo, algo como:

<p align="center">
  <img src="/images/image7.png" width="350" title="hover text">
</p>

Após isso você pode utilizar a callback dentro de seu módulo sem problemas.

IMPORTANTE: A ordem em que você declara seu módulo no seu GM principal vai interferir na ordem de acontecimentos, por exemplo: Você criou um módulo onde dá pontos para uma pessoa ao matar alguém e também cria um módulo onde salva as contas ao desconectar, se você declarar o módulo de salvar ao desconectar antes do módulo de dar pontos a pessoa, não irá salvar os pontos pelo fato da ordem (Espero que isso tenha ficado claro pois é muito importante).

## 📃 Útil.

Algumas informações úteis estarão nesta aula.

Includes - Ao declarar uma include no GM principal, ela será vinculada a todos os módulos, por tanto não é necessário declarar uma include duas vezes.

Comandos - A utilização de comandos é totalmente permitida nos módulos, você pode utilizar tanto a Callback nativa quanto um processador de comandos como ZCMD ou Pawn.CMD, basta declara-lo no GM principal.

Órdem dos módulos: Já citei antes mas é importante; A ordem em que você declara seu módulo no seu GM principal vai interferir na ordem de acontecimentos, por exemplo: Você criou um módulo onde dá pontos para uma pessoa ao matar alguém e também cria um módulo onde salva as contas ao desconectar, se você declarar o módulo de salvar ao desconectar antes do módulo de dar pontos a pessoa, não irá salvar os pontos pelo fato da ordem.

Exagear - Provavelmente a biblioteca YSI não será compilada no Exagear, impossibilitando o uso da modularização pelo y_hooks. :(

Erros: Qualquer erro ortográfico ou alguma dúvida na utilização, me contate em meu discord: gomaink#3403
