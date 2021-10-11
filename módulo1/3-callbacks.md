<h1>
    3. Callbacks.
</h1>

Usar callbacks en m�dulos es muy simple, simplemente cambie el nombre "public" a "hook" en su m�dulo, ejemplo: 

<p align="center">
  <img src="/images/image7.png" width="350" title="hover text">
</p>

Despu�s de eso, puede usar el callback dentro de su m�dulo sin ning�n problema.

IMPORTANTE: El orden en el que declares tu m�dulo en tu script principal interferir� con el orden de los hooks, por ejemplo: Si creaste un m�dulo donde le das puntos a una persona por matar a alguien y tambi�n creas un m�dulo donde guardas cuentas al desconectarse, si incluyes el m�dulo de guardar al desconectarse antes del m�dulo de dar los puntos, no guardar� los puntos debido al orden (espero que est� claro, ya que es muy importante).