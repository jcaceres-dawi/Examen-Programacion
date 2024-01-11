# Examen Programación
## Bloque 1
### Ejercicio 1
Haz una función **decimalBinario** que reciba por parámetro un número entero decimal y lo muestre por pantalla en binario. Con una cifra por línea y puede estar invertido. Se asume que el número que se pasa por parámetro siempre es positivo.
```java
public class act1 {

    public static void main(String[] args) {
        int num = 1234;
        decimalBinari(num);
    }

    public static void decimalBinari(int num) {
        int resto;
        while (num > 0) {
            resto = num % 2;
            num = num / 2;
            System.out.println(resto);
        }
    }
}
```
### Ejercicio 2
Haz una función **binarioDecimal** que reciba por parámetro un número entero binario (tipo long) y muestre por pantalla el número decimal. Para pasar de binario a decimal se tiene que multiplicar cada término por 2^n donde n es la posición que ocupa el dígito (de derecha a izquierda y empezando en 0) y sumar el resultado de todas las multiplicaciones.
```java
public class act2 {
    public static void main(String[] args) {
        long num = 1111;
        binariDecimal(num);
    }

    public static void binariDecimal(long num) {
        long resto;
        int exponente = 0;
        int decimal = 0;

        while (num != 0) {
            resto = num % 10;
            num = num / 10;
            decimal = (int) (decimal + (resto * Math.pow(2, exponente)));
            exponente++;
        }
        System.out.println(decimal);
    }
}
```
