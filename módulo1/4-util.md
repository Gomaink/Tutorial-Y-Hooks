<h1>
    4. �til.
</h1>

En esta clase habr� informaci�n �til.

Includes: Al declarar una inclusi�n en el script principal, se vincular� a todos los m�dulos, por lo que no es necesario declarar una inclusi�n dos veces.

Comandos: El uso de comandos est� totalmente permitido en los m�dulos, puede usar el callback nativo o un procesador de comandos como ZCMD o Pawn.CMD, simplemente decl�relo en el script principal.

Orden de los m�dulos: Lo he mencionado antes, pero es importante; El orden en el que incluyas tu m�dulo en tu script principal interferir� con el orden de los callbacks, por ejemplo: Si creaste un m�dulo donde le das puntos a una persona por matar a alguien y tambi�n creas un m�dulo donde guardas cuentas al desconectarse, si usted declara el m�dulo de guardar al desconectarse antes de que el m�dulo d� puntos a la persona, no guardar� los puntos debido al orden.

Exagear: Probablemente la biblioteca YSI no es compatible con Exagear, lo que hace imposible el uso de la modularizaci�n por y_hooks. :(

Errores: Cualquier error de ortograf�a o pregunta, cont�cteme en mi discord: Gomainkk#3403 