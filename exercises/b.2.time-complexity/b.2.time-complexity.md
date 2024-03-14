# Time Complexity

## Calcula la complejidad algorítmica Big O de los siguientes algoritmos

1. Módulo

   ```c
   int mod(int a, int b) {
       if (b <=a) return -1;
       int div = a / b;
       return a - div * b;
   }
   ```

   - BigO = 0(1)

2. Multiplicación

   ```c
   int product(int a, int b) {
       int sum = 0; // O(1)
       for (int I = 0; I < b; I++) { // init O(1) ;
           sum += a; // O(3)
       }
       return sum;
   }
   ```

   - BigO mejor caso = O(1); cuando b <= 1
   - BigO peor caso = O(n)

3. Potencia

   ```c
   static int power(int a, int b) {
       if (b < 0) return a; // O(1)
       if (b == 0) return 1; // O(1)
       int sum = a; // O(1)
       for (int I = 0; I < b - 1; I++) { // Init O(1); b === 1 ? O(1) : O(n)
           sum *= a;
       }
       return sum;
   }
   ```

   - BigO mejor caso = O(1); cuando b <= 1
   - BigO peor caso = O(n)

4. División

   ```c
   int div(int a, int b) {
       int count = a; // O(1)
       int sum = b; // O(1)
       while (sum <= a) { // Init O(1); a > b ? O(1) : O(n)
           sum += b;
           count++;
       }
       return count;
   }
   ```

   - BigO mejor caso = O(1); cuando a > b
   - BigO peor caso = O(n)

5. Copiar un array

   ```c
   int[] copyArray(int[] array) {
       int[] copy = new int[0]; // O(3)
       for (int value : array) { // O(n)
           copy = appendToNew(copy, value);
       }
       return copy;
   }
   int[] appendToNew(int[] array, int value) {
       int[] bigger = new int[array.length + 1];
       for (int I = 0; I < array. length; I++) {
           bigger[I] = array[I];
       }
       bigger[bigger.length - 1] = value;
       return bigger;
   }
   ```

   - BigO = 0(n^2)

6. Raíz Cuadrada

   ```c
   int sqrt(int n) {
       return sqrt_helper(n, 1, n);
   }

   int sqrt_helper(int n, int min, int max) {
       if (max < min) return -1;
       int guess = (min + max) / 2;
       if (guess * guess == n) {
           return guess;
       } else if (guess *guess <n) {
           return sqrt_helper(n, guess + 1, max) ;
       } else {
           return sqrt_helper(n, min, guess - 1);
       }
   }
   ```

   - BigO = O(log n)

## Implementación pensando en la complejidad

Construye una función que dado un número entero positivo, devuelva el valor de el fibonacci de ese número, considerando que los primeros dos valores de fibonacci son fib(0)=0 y fib(1)=1 respectivamente. Ejemplo: fib(6) = 8, fib(60)=1548008755920.

A ese algoritmo que has construido, calcula su complejidad algorítmica y su complejidad ciclomática.

- _¿Qué ocurre a la función cuando el número de entrada n crece?_

- Ejecuta tu función para diferentes valores crecientes (al menos unos 10 valores ) midiendo el tiempo y poniéndolo en una gráfica. _¿Qué forma tiene la función?_
