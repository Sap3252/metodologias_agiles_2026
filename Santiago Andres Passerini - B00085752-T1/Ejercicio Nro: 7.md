# Ejercicio Nro: 7

## Enunciado
Dar un ejemplo de cada uno de los cuellos de botellas analizados anteriormente en el paper de Brooks.

## Resolución
En su ensayo, Brooks argumenta que la complejidad es la esencia del software. Para comprender los cuellos de botella, analicemos un sistema de gran escala como Mercado Libre
+ Dificultad Accidental: Alude a los inconvenientes derivados de la ejecución técnica.
Un caso específico sería el tiempo invertido por los programadores al configurar a mano cada servidor para compatibilizarlo con el lenguaje de código utilizado.
En el pasado esto representaba una barrera enorme, que actualmente se redujo drásticamente mediante el uso de Cloud Computing (AWS) y las utilidades de automatización.
Es decir, el "obstáculo" de infraestructura es accidental ya que no se relaciona con el negocio de vender artículos, sino con los instrumentos de desarrollo.
+ Dificultad Esencial: Representa el auténtico límite y es imposible de suprimir con tecnología.
En Mercado Libre, el reto esencial radica en la lógica del negocio: la forma de sincronizar en milisegundos el inventario de un vendedor en una zona, junto con el pago de un comprador en otra, calculando tarifas de envío y normas fiscales regionales.
Dicha profundidad conceptual es inherente al problema.
Incluso aplicando la IA más avanzada, el desafío de estructurar esta lógica comercial perdurará, pues conforma la esencia de lo que el programa debe hacer
