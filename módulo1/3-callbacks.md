<h1>
    3. Callbacks.
</h1>

Usar callbacks en módulos es muy simple, simplemente cambie el nombre "public" a "hook" en su módulo, ejemplo: 

<p align="center">
  <img src="/images/image7.png" width="350" title="hover text">
</p>

Después de eso, puede usar el callback dentro de su módulo sin ningún problema.

IMPORTANTE: El orden en el que declares tu módulo en tu script principal interferirá con el orden de los hooks, por ejemplo: Si creaste un módulo donde le das puntos a una persona por matar a alguien y también creas un módulo donde guardas cuentas al desconectarse, si incluyes el módulo de guardar al desconectarse antes del módulo de dar los puntos, no guardará los puntos debido al orden (espero que esté claro, ya que es muy importante).