# Tarea "Juego de dados

## Clases, Atributos y Métodos:
1. Dado *(Clase)*:
   1. caraSuperior(int) *(Atributo)*: Representa el valor del dado (1-6).
   2. lanzar() *(Método)*: Simula el lanzamiento del dado.
   3. getCaraSuperior() *(Método)*: Retorna el valor de *caraSuperior()*.
2. JuegoDeDados *(Clase)*:
   1. dado1 *(Atributo)*: Instancia 1er dado.
   2. dado2 *(Atributo)*: Instancia 2do dado.
   3. calculadora *(Atributo)*: Calcula sumas.
   4. jugar() *(Método)*: Simula el lanzamiento de ambos dados, después suma los valores de las caras superiores y determina si el jugador fanó o perdió.
   5. getSumaCaras() *(Método)*: Retorna el valor de la suma de las caras superiores de ambos dados.
3. Calculadora *(Clase)*:
   1. num1 / num2 *(Atributos)*.
   2. sumar(int num1, int num2) *(Método)*: Retorna la suma entre num1 y num2.

## Relaciones entre clases:
1. JuegoDeDados y Dado *(Composición)*: Cada "JuegoDeDados" tiene 2 "Dados", por lo tanto, los dados son creados específicamente para cada juego.
2. JuegoDeDados y Calculadora *(Agregación)*: "JuegoDeDados" utiliza a "Calculadora", ya que necesita la funcionalidad de "sumar" para el correcto funcionamiento del juego.

## Diagrama UML y VP:
    "en progreso..."

## Codificación de la solución:
     ingresar a: -> src/main/dados