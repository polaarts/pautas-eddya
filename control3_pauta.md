## CONTROL 3 (Pauta) - Estructura de Datos y Algoritmos 

### PRIMERA PARTE - 20 puntos

Implementa una funcion `mergeSort` que reciba un arreglo de números enteros y lo ordene en orden descendente utilizando el algoritmo de Merge Sort.

#### SOLUCIÓN:

```java 
class MergeSort {

  public static void main(String[] args) {
    int[] arr = { 5, 4, 3, 2, 1 };
    arr = mergeSort(arr);
    for (int i = 0; i < arr.length; i++) {
      System.out.println(arr[i]);
    }
  }

  static int[] mergeSort(int[] arr) {

    if (arr.length <= 1) {
      return arr;
    }

    int[] left = new int[arr.length / 2];
    int[] right = new int[arr.length - left.length];

    for (int i = 0; i < left.length; i++) {
      left[i] = arr[i];
    }
    for (int i = 0; i < right.length; i++) {
      right[i] = arr[i + left.length];
    }

    left = mergeSort(left);
    right = mergeSort(right);

    int i = 0, j = 0, k = 0;
    while (left.length != j && right.length != k) {
      if (left[j] < right[k]) {
        arr[i] = left[j];
        j++;
      } else {
        arr[i] = right[k];
        k++;
      }
      i++;
    }

    while (left.length != j) {
      arr[i] = left[j];
      j++;
      i++;
    }

    while (right.length != k) {
      arr[i] = right[k];
      k++;
      i++;
    }

    return arr;

  }
}
```

### SEGUNDA PARTE - 20 puntos, 5 puntos c/u

#### Para cada una de las siguientes afirmaciones, denote su veracidad con la letra V o su falsedad con la letra F. Para las respuestas falsas justifique su respuesta.

1. **F** - El algoritmo de búsqueda binaria puede aplicarse a cualquier arreglo, sin importar si está ordenado o no.

   - El algoritmo funciona dividiendo el arreglo en mitades y comparando el elemento central con el valor buscado para decidir en qué mitad continuar la búsqueda. Si el arreglo no está ordenado, no se puede garantizar que el algoritmo encontrará el elemento correcto, ya que la premisa de comparar con el elemento central y decidir en qué mitad seguir se basa en que los elementos están en un orden específico.

2. **F** - El algoritmo de merge sort es un algoritmo de ordenamiento in-place.
    
    - El algoritmo de merge sort no es un algoritmo de ordenamiento in-place. Merge sort requiere espacio adicional proporcional al tamaño del arreglo que se está ordenando. Durante el proceso de fusión, se crean arreglos temporales para almacenar las mitades que se están fusionando. 

3. **F** - El algoritmo de ordenamiento burbuja (bubble sort) es mas eficiente que el algoritmo de merge sort para grandes volúmenes de datos.

    - Bubble sort tiene una complejidad temporal de O(𝑛²) en el peor de los casos. Esto significa que el tiempo que tarda en ordenar los datos crece cuadráticamente con el tamaño del conjunto de datos. Mientras que merge sort tiene una complejidad temporal de O(𝑛 log 𝑛) en el peor de los casos. Esto significa que el tiempo que tarda en ordenar los datos crece de forma logarítmica con el tamaño del conjunto de datos. Por lo tanto, merge sort es más eficiente que bubble sort para grandes volúmenes de datos.

4. **F** - La búsqueda secuencial o lineal tiene una complejidad temporal de O(n²) en el peor de los casos.

    - La búsqueda secuencial o lineal tiene una complejidad temporal de O(𝑛) en el peor de los casos. En una búsqueda lineal, cada elemento del arreglo se examina una vez hasta encontrar el elemento buscado o recorrer todo el arreglo. Por lo tanto, si hay 𝑛 elementos en el arreglo, en el peor de los casos, se realizarán 𝑛 n comparaciones. Esto resulta en una complejidad temporal lineal O(𝑛), no cuadrática.

### TERCERA PARTE - 20 puntos, 10 puntos c/u

Describe el funcionamiento del siguiente algoritmo y su complejidad en términos de O(f(𝑛)).


```java
int mistery(int arr[], int x) {
  int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == x) {
        return mid;
        }
        if (arr[mid] < x) {
        low = mid + 1;
        } else {
        high = mid - 1;
        }
    }
    return -1;
}
```

#### SOLUCIÓN:

El algoritmo es una implementación de la búsqueda binaria. La búsqueda binaria es un algoritmo de búsqueda que encuentra la posición de un valor en un arreglo ordenado. El algoritmo compara el valor buscado con el valor en la mitad del arreglo. Si el valor buscado es igual al valor en la mitad del arreglo, se devuelve la posición de ese valor. Si el valor buscado es menor que el valor en la mitad del arreglo, se busca en la mitad inferior del arreglo. Si el valor buscado es mayor que el valor en la mitad del arreglo, se busca en la mitad superior del arreglo. Este proceso se repite hasta que se encuentra el valor buscado o se determina que el valor no está en el arreglo.

La complejidad temporal de la búsqueda binaria es O(log n). En cada iteración, el tamaño del conjunto de datos se reduce a la mitad. Por lo tanto, el tiempo que tarda en encontrar el valor buscado crece de forma logarítmica con el tamaño del conjunto de datos.