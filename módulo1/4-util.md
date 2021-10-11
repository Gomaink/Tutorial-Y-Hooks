<h1>
    4. Útil.
</h1>

En esta clase habrá información útil.

Includes: Al declarar una inclusión en el script principal, se vinculará a todos los módulos, por lo que no es necesario declarar una inclusión dos veces.

Comandos: El uso de comandos está totalmente permitido en los módulos, puede usar el callback nativo o un procesador de comandos como ZCMD o Pawn.CMD, simplemente declárelo en el script principal.

Orden de los módulos: Lo he mencionado antes, pero es importante; El orden en el que incluyas tu módulo en tu script principal interferirá con el orden de los callbacks, por ejemplo: Si creaste un módulo donde le das puntos a una persona por matar a alguien y también creas un módulo donde guardas cuentas al desconectarse, si usted declara el módulo de guardar al desconectarse antes de que el módulo dé puntos a la persona, no guardará los puntos debido al orden.

Exagear: Probablemente la biblioteca YSI no es compatible con Exagear, lo que hace imposible el uso de la modularización por y_hooks. :(

Errores: Cualquier error de ortografía o pregunta, contácteme en mi discord: Gomainkk#3403 