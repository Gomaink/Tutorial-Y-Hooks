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

O uso de callbacks em módulos é bastante simples e segue uma estrutura padronizada graças ao y_hooks. Veja como configurar corretamente e entender a importância da ordem de declaração.

### 1. Substituindo public por hook

Ao definir callbacks dentro de seus módulos, substitua a palavra-chave public por hook. Isso permite que o callback seja gerenciado pelo sistema de modularização do y_hooks.

Exemplo:
```c
hook OnPlayerDeath(playerid, killerid, reason)  
{  
    // Seu código aqui  
}  
```
<p align="center">
  <img src="/images/image7.png" width="350" title="Exemplo de Callback com hook">
</p>  

Com isso, você pode usar as callbacks normalmente dentro do módulo, sem conflitos com o gamemode principal.

### 2. Atenção à Ordem de Declaração

A ordem em que os módulos são declarados no seu gamemode principal afeta diretamente o comportamento das callbacks.

Por exemplo:
- Módulo A: Dá pontos ao jogador ao matar alguém.
- Módulo B: Salva os dados da conta ao desconectar.

Se você incluir o Módulo B (salvar dados) antes do Módulo A (dar pontos), os pontos concedidos ao jogador podem não ser salvos, porque o módulo de salvamento será executado antes de o módulo de pontuação completar sua lógica.

Para evitar problemas:
- Organize seus módulos no arquivo principal com base na prioridade das ações.
- Certifique-se de que as ações mais importantes sejam concluídas antes das menos críticas.

## 📃 Útil.

Nesta seção, você encontrará algumas informações e dicas importantes para utilizar módulos de forma eficiente e evitar problemas comuns.

### 1. Includes nos Módulos
- Ao declarar uma include no gamemode principal, ela será automaticamente vinculada a todos os módulos.
- Não é necessário declarar a mesma include em cada módulo.
- Isso mantém seu código mais limpo e evita redundâncias.

### 2. Comandos nos Módulos
- Você pode criar comandos dentro dos módulos sem restrições.
- Use tanto a callback nativa OnPlayerCommandText quanto processadores de comandos como ZCMD ou Pawn.CMD.
- Basta declarar o processador no gamemode principal, e ele estará disponível para os módulos.


### 3. Ordem de Declaração dos Módulos
- A ordem dos módulos importa!
- Os módulos são processados na sequência em que são declarados no gamemode principal.
- Por exemplo:
- Módulo A: Dá pontos ao jogador.
- Módulo B: Salva os dados do jogador.
- Se o Módulo B for declarado antes do Módulo A, os pontos podem não ser salvos.

### Dica: 
Sempre organize seus módulos com base nas prioridades de execução.

### 4. Compatibilidade com Exagear
- Infelizmente, a biblioteca YSI (incluindo o y_hooks) pode não ser compilada corretamente no Exagear, tornando impossível a modularização neste ambiente.
- Caso precise usar Exagear, considere uma abordagem manual de modularização ou busque alternativas mais simples.