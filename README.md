# Examen Programación
## Bloque 1
### Ejercicio 1
Haz una función **decimalBinario** que reciba por parámetro un número entero decimal y lo muestre en pantalla en binario. Con una cifra por línea y puede estar invertido. Se asume que el número que se pasa por parámetro siempre es positivo.
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
