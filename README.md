# Tarea "Juego de dados"

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
### Dado:
    package dados;

    import java.util.Random;

    /**
    * Representa un dado de 6 caras
    */
    public class Dado {
        private int caraSuperior;
        private Random random;

        public Dado() {
            this.random = new Random(); //Dado sin cara superior definida
        }

        public void lanzar() {
            this.caraSuperior = random.nextInt(6) + 1; //Genera valor aleatorio entre 1 y 6 para el dado.
        }

        public int getCaraSuperior() {
            return caraSuperior;
        }
    }

### Juego de dados:
    package dados;

    public class JuegoDeDados {
        private Dado dado1;
        private Dado dado2;
        private Calculadora calculadora;

        /**
        * Inicializa 2 dados y la calculadora.
        * @param calculadora para utilizar sumas.
        */
        public JuegoDeDados(Calculadora calculadora) {
            this.dado1 = new Dado();
            this.dado2 = new Dado();
            this.calculadora = calculadora;
        }

        /**
        * Simula la ronda del juego.
        * @return true si la suma de ambas caras en 7 (gg), false en caso contrario.
        */
        public boolean jugar() {
            dado1.lanzar();
            dado2.lanzar();

            int sumaCaras = calculadora.sumar(dado1.getCaraSuperior(), dado2.getCaraSuperior());

            System.out.println("Dado 1: " + dado1.getCaraSuperior() + " | Dado 2: " +  dado2.getCaraSuperior());
            System.out.println("Suma de las caras: " + sumaCaras);

            return sumaCaras == 7;
        }

        /**
        * Para testing.
        * @return suma de las caras superiores de ambos dados.
        */
        public int getSumaCaras() {
            return calculadora.sumar(dado1.getCaraSuperior(), dado2.getCaraSuperior());
        }

        //Métodos de acceso a dados individuales, en caso de testing.
        public Dado getDado1() {
            return dado1;
        }

        public Dado getDado2() {
            return dado2;
        }
    }

### Calculadora:
    package dados;

    /**
    * Calculadora simple que suma dos enteros
    */
    public class Calculadora {
        public int sumar(int num1, int num2) {
            return num1 + num2;
        }
    }


    
