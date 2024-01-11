# Examen Programación
## Bloque 1
### Ejercicio 1
Haz una función **decimalBinari** que reciba por parámetro un número entero decimal y lo muestre por pantalla en binario. Con una cifra por línea y puede estar invertido. Se asume que el número que se pasa por parámetro siempre es positivo.
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
Haz una función **binariDecimal** que reciba por parámetro un número entero binario (tipo long) y muestre por pantalla el número decimal. Para pasar de binario a decimal se tiene que multiplicar cada término por 2^n donde n es la posición que ocupa el dígito (de derecha a izquierda y empezando en 0) y sumar el resultado de todas las multiplicaciones.
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
### Ejercicio 3
Haz una función **esParell** que reciba por parámetro un número entero y devuelva un booleano _true_ si es par o _false_ si no lo es.
```java
public class act3 {
    public static void main(String[] args) {
        int num = 58383834;
        System.out.println(esParell(num));
    }

    public static boolean esParell(int num) {
        if (num % 2 == 0) {
            return true;
        } else {
            return false;
        }
    }
}
```
### Ejercicio 4
Haz una función **primersNombresParells** que reciba por parámetro un número entero _n_ y muestre por pantalla todos los nombres pares entre 0 (incluido) y _n_ (incluido si es necesario). Se asume que el número _n_ es siempre positivo.
```java
public class act4 {
    public static void main(String[] args) {
        int num = 10;
        primersNombresParells(num);
    }

    public static void primersNombresParells(int num) {
        for (int i = 0; i <= num; i++) {
            if (i % 2 == 0) {
                System.out.println(i);
            }
        }
    }
}
```
