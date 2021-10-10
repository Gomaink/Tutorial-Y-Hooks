<h1>
    4. Útil.
</h1>

Algumas informações úteis estaram nesta aula.

Includes - Ao declarar uma include no GM principal, ela será vinculada a todos os módulos, por tanto não é necessário declarar uma include duas vezes.

Comandos - A utilização de comandos é totalmente permitida nos módulos, você pode utilizar tanto a Callback nativa quanto um processador de comandos como ZCMD ou Pawn.CMD, basta declara-lo no GM principal.

Órdem dos módulos: Já citei antes mas é importante; A ordem em que você declara seu módulo no seu GM principal vai interferir na ordem de acontecimentos, por exemplo: Você criou um módulo onde dá pontos para uma pessoa ao matar alguém e também cria um módulo onde salva as contas ao desconectar, se você declarar o módulo de salvar ao desconectar antes do módulo de dar pontos a pessoa, não irá salvar os pontos pelo fato da ordem.

Exagear - Provavelmente a biblioteca YSI não será compilada no Exagear, impossibilitando o uso da modularização pelo y_hooks. :(