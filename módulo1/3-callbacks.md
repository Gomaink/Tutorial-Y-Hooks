<h1>
    3. Callbacks.
</h1>

Para a utilização de callbacks em módulos é bem simples, você deve apenas trocar o nome "public" por "hook" em seu módulo, algo como:

<p align="center">
  <img src="/images/image7.png" width="350" title="hover text">
</p>

Após isso você pode utilizar a callback dentro de seu módulo sem problemas.

IMPORTANTE: A ordem em que você declara seu módulo no seu GM principal vai interferir na ordem de acontecimentos, por exemplo: Você criou um módulo onde dá pontos para uma pessoa ao matar alguém e também cria um módulo onde salva as contas ao desconectar, se você declarar o módulo de salvar ao desconectar antes do módulo de dar pontos a pessoa, não irá salvar os pontos pelo fato da ordem (Espero que isso tenha ficado claro pois é muito importante).