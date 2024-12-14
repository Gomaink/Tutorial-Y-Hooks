# Tutorial-Y-Hooks
> Um breve tutorial sobre a utilização da include y_hooks para a modularização de sistemas no SA-MP.

<br>

1. [Instalação](#-Instalação)

2. [Utilização](#-Utilização)

3. [Callbacks](#-Callbacks)

3. [Útil](#-Útil)
   
<br>

## 🚀 Instalação

A instalação da biblioteca YSI, criada por Y_Less, é uma etapa fundamental para muitos projetos no SA:MP. Apesar de parecer complicada, é um processo simples e rápido.

### 1. Baixando a Biblioteca

Acesse o GitHub oficial do Y_Less ou opte pelo download direto via MediaFire.
- GitHub: https://github.com/pawn-lang/YSI-Includes
- Para baixar: clique no botão Code e depois em Download ZIP, como mostrado na imagem:

<p align="center">
  <img src="/images/image2.png" width="350" title="Baixando pelo GitHub">
</p>  

- MediaFire: https://www.mediafire.com/file/koiqd2q9m2thelf/YSI-Includes.zip/file
- Para baixar: clique no botão Download, como indicado na imagem:

<p align="center">
  <img src="/images/image1.png" width="350" title="Baixando pelo MediaFire">
</p>  

Ambas as opções oferecem o mesmo conteúdo, escolha a que for mais conveniente.

### 2. Extraindo os Arquivos

Após concluir o download:
#### 1.	Localize o arquivo ZIP (geralmente chamado YSI-Includes.zip).
#### 2.	Extraia o conteúdo utilizando um programa como WinRAR ou 7-Zip.
#### 3.	Após a extração, você verá uma pasta chamada YSI-Includes ou algo similar:

<p align="center">
  <img src="/images/image3.png" width="350" title="Arquivos Extraídos">
  </p>  


### 3. Movendo os Arquivos

Agora, é hora de integrar a biblioteca ao seu projeto:
#### 1.	Clique com o botão direito na pasta extraída e selecione Copiar.
#### 2.	Navegue até o diretório onde seu gamemode está localizado.
#### 3.	Dentro da pasta do gamemode, vá para pawno/includes.
#### 4.	Cole a pasta YSI-Includes nesse local.

### 4. Conferindo a Instalação

Após mover os arquivos, certifique-se de que o diretório pawno/includes contém os arquivos necessários da biblioteca YSI. Se tudo foi feito corretamente, você poderá utilizá-la no seu gamemode sem problemas.

### Dica: 
É importante garantir que a versão da biblioteca seja compatível com o restante do seu projeto. Sempre que possível, utilize a versão mais recente disponível no GitHub.

## ☕ Utilização

Vamos aprender como criar uma pasta dedicada aos módulos e configurá-los corretamente.

### 1. Criando a Pasta de Módulos

Antes de tudo, é necessário criar uma pasta onde os módulos serão armazenados.
- Ela deve estar na pasta principal do seu gamemode.
- Não utilize espaços ou números no nome da pasta.
- Um bom nome seria algo como modulos ou modules.

<p align="center">
  <img src="/images/image4.png" width="350" title="Pasta de Módulos">
</p>  


### 2. Criando os Arquivos de Módulos

Dentro da pasta criada, você precisará adicionar arquivos para os módulos.
- Esses arquivos podem ter extensões como .pwn, .inc, ou .sys, dependendo do propósito de cada módulo.

<p align="center">
  <img src="/images/image5.png" width="350" title="Arquivos de Módulos">
</p>  


### 3. Configurando os Módulos

Agora, vamos configurar os módulos para que funcionem corretamente no seu gamemode.

#### a) Incluindo a Biblioteca y_hooks

Cada módulo deve incluir a biblioteca y_hooks, que será responsável por gerenciar a modularização do código.
Adicione o seguinte código no início de cada arquivo de módulo:

```c
#include <YSI-Includes\YSI_Coding\y_hooks>  
```

<p align="center">
  <img src="/images/image6.png" width="350" title="Include y_hooks">
</p>  


Nota: A biblioteca y_hooks é parte da biblioteca YSI, então certifique-se de que a YSI já esteja instalada no seu projeto (veja a seção anterior sobre instalação).

#### b) Vinculando os Módulos ao Gamemode

Para que o gamemode reconheça os módulos criados, você precisa vinculá-los. Isso é feito com o comando #include, apontando para a localização do módulo.
Adicione a seguinte linha no seu gamemode:

```c
#include "../suapastademodulos/nomedoseumodulo"  
```

- suapastademodulos: Substitua pelo nome da pasta onde os módulos estão armazenados (por exemplo, modulos).
- nomedoseumodulo: Substitua pelo nome do arquivo do módulo que você deseja incluir.

### Dica: 
Você pode organizar as inclusões no início do seu gamemode (antes da função main) ou no final do arquivo, conforme preferir.

<p align="center">
  <img src="/images/image8.png" width="350" title="Vinculando o Módulo ao Gamemode">
</p>  


### 4. Regras Importantes
- Inclua y_hooks em Todos os Módulos:
Cada módulo criado deve ter a biblioteca y_hooks incluída no topo do arquivo. Sem isso, a modularização não funcionará corretamente.
- Evite Nomes Duplicados:
Certifique-se de que os nomes dos módulos e funções não entrem em conflito com outros módulos ou com o gamemode principal.

Com esses passos, você estará pronto para criar módulos organizados e vinculá-los ao seu gamemode. Modularizar o código não apenas melhora a organização, mas também facilita a adição de novas funcionalidades no futuro.

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
