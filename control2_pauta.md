## CONTROL 2 (Pauta) - Estructura de Datos y Algoritmos 

### PRIMERA PARTE - 20 puntos

Diseñe un algoritmo que recibe como entrada un string que puede estar compuesto por los siguientes caracteres:

                                []{}()

Como output el algoritmo debe retornar un booleano que describa si la expresion armada es válida, es decir que para cada símbolo de apertura, existe un símbolo de cierre en el lugar correcto.

Ejemplo 1:

- Input: {()[]}
- Output: True

Ejemplo 2:

- Input: {}()[(]
- Output: False

#### SOLUCIÓN:

```java
import java.util.Stack;

public class Solution {

  static boolean checkBalancedParentheses(String s) {
    Stack<Character> stack = new Stack<>();
    for (int i = 0; i < s.length(); i++) {
      if (s.charAt(i) == '(' || s.charAt(i) == '[' || s.charAt(i) == '{') {
        stack.push(s.charAt(i));
      } else {
        char top = stack.pop();
        if (s.charAt(i) == ')' && top == '(') {
        } else if (s.charAt(i) == ']' && top == '[') {
        } else if (s.charAt(i) == '}' && top == '{') {
        } else {
          return false;
        }
      }
    }
    if (stack.isEmpty()) {
      return true;
    }
    return false;
  }

  public static void main(String[] args) {
    System.out.println(check("{()")); // true
    System.out.println(check("()[]{}")); // true
    System.out.println(check("(]")); // false
    System.out.println(check("([)]")); // false
    System.out.println(check("{[]}")); // true
  }
}
```

### SEGUNDA PARTE - 20 puntos, 5 puntos c/u

#### Para cada una de las siguientes afirmaciones, denote su veracidad con la letra V o su falsedad con la letra F. Para las respuestas falsas justifique su respuesta.

1. **F** - Elimina el primer nodo de una lista enlazada tiene complejidad de tiempo O(n).

   - La complejidad de tiempo es O(1) ya que solo se debe cambiar el puntero del primer nodo.

2. **V** - Una stack (pila) sigue el principio LIFO (Last In First Out), lo que significa que el último elemento en ser añadido es el primero en ser removido.

3. **F** - La inserción al final de una linked list es más eficiente que la inserción al principio.

    - Si se tiene referencia al "tail" el tiempo es el mismo.

4. **V** - Eliminar un nodo de una linked list requiere modificar solo los enlaces de los nodos adtacentes al nodo eliminado.

### TERCERA PARTE - 20 puntos, 10 puntos c/u

Describa el funcionamiento del siguiente algoritmo, determinando las restricciones del conjunto de entrada (para qué valores estos alogritmos funcionan) y su complejidad en términos de O(f(n)).

 ```java
    static int f(int n) {
        if (n == 0) {
            return 0;
        }
        return n + f(n - 1);
    }
```

#### SOLUCIÓN:

   - Funcionamiento: Se encarga de hacer una sumatoria del 1 hasta n
   - Restricciones: n >= 0
   - Complejidad: O(n)

 ```java
    static int f(int n) {
        if (n <= 1) {
            return 0;
        }
        return f(n / 2) + 1;
    }
```

#### SOLUCIÓN:

   - Funcionamiento: Se encarga de devolver el logaritmo en base 2 de n
   - Restricciones: n : reales
   - Complejidad: O(log(n))