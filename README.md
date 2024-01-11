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
### Ejercicio 5
Haz una función **menu** que muestre el siguiente menú por pantalla y devuelva la opción escogida por el usuario en formato número entero.
_Tria una de les següents opcions:_  
_1. Decimal a binari_  
_2. Binaria a decimal_  
_3. És parell?_  
_4. Calcular parells de 0 fins a n_  
_0. Sortir_
```java
public class act5 {
    public static void main(String[] args) {
        menu();
    }

    public static int menu() {
        Scanner sc = new Scanner(System.in);
        System.out.println("Tria una de les següents opcions:");
        System.out.println("1. Decimal a binari");
        System.out.println("2. Binaria a decimal");
        System.out.println("3. És parell?");
        System.out.println("4. Calcular parells de 0 fins a n");
        System.out.println("0. Sortir");
        int opcion = sc.nextInt();
        sc.close();
        return opcion;
    }
}
```
### Ejercicio 6
Implementa el **main**, que consiste en:  
a) Mostrar el _menu_ principal, si el usuario introduce un 0, el programa acaba, si introduce una opción inválida se le informa y se le vuelve a mostrar el menú.  
b) Preguntar los datos necesarios para ejecutar la función que corresponde haciendo uso de los ejercicios anteriores.  
c) Vuelve a mostrar el menú
```java
import java.util.Scanner;

public class act6 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int opcion = menu();
        switch (opcion) {
            case 0:
                System.exit(opcion);
                break;
            case 1:
                System.out.println("Escribe un número entero decimal");
                int decimal = sc.nextInt();
                decimalBinari(decimal);
                opcion = menu();
                break;
            case 2:
                System.out.println("Escribe un número binario");
                int binario = sc.nextInt();
                binarioDecimal(binario);
                opcion = menu();
                break;
            case 3:
                System.out.println("Escribe un número para saber si es par");
                int num1 = sc.nextInt();
                System.out.println(esParell(num1));
                opcion = menu();
                break;
            case 4:
                System.out.println("Escribe un número para saber los pares entre 0 y el número");
                int num2 = sc.nextInt();
                primersNombresParells(num2);
                opcion = menu();
                break;
            default:
                System.out.println("Opció no vàlida");
                opcion = menu();
                break;
        }
    }

    public static int menu() {
        Scanner sc = new Scanner(System.in);
        System.out.println("Tria una de les següents opcions:");
        System.out.println("1. Decimal a binari");
        System.out.println("2. Binaria a decimal");
        System.out.println("3. És parell?");
        System.out.println("4. Calcular parells de 0 fins a n");
        System.out.println("0. Sortir");
        int opcion = sc.nextInt();
        return opcion;
    }
}
```
