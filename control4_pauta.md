## CONTROL 4 (Pauta) - Estructura de Datos y Algoritmos

### PRIMERA PARTE - 20 puntos

Se define el nodo de un arbol binario de la siguiente forma:

```java
public class TreeNode {
  int val;
  TreeNode left;
  TreeNode right;
  TreeNode(int val) { this.val = val; }
}
```

Defina el método `invertTree(TreeNode root)` el cual recibe la raíz de un árbol binario, invierte el árbol (todos los nodos derechos pasan a ser izquierdos y viceversa) y retorna la raíz del árbol invertido.

```java
public TreeNode invertTree(TreeNode root) {
  if (root == null) {
    return null;
  }
  TreeNode left = invertTree(root.left);
  TreeNode right = invertTree(root.right);
  root.left = right;
  root.right = left;
  return root;
}
```

### SEGUNDA PARTE - 20 puntos, 5 puntos c/u

#### Para cada una de las siguientes afirmaciones, denote su veracidad con la letra V o su falsedad con la letra F. Para las respuestas falsas justifique su respuesta.

1. **F** - En un BST, la inserción de un nuevo nodo siempre toma tiempo O(1)

   - El tiempo promedio de inserción en un BST es O(log n), donde n es el número de nodos en el árbol. Sin embargo, en el peor de los casos, la inserción puede tomar tiempo O(n).

2. **V** - Un Heap está siempre balanceado.

3. **V** - El proceso de eliminar el valor máximo de un max-heap implica intercambiar el nodo raíz con el último nodo y luego ajustar el heap.

4. **F** - Un BST está siempre balanceado.

   - Un BST se define por la propiedad de que para cada nodo, el valor de su clave es mayor que el valor de cualquier clave en su subárbol izquierdo y menor que el valor de cualquier clave en su subárbol derecho. Esto último, no implica necesariamente que el árbol esté balanceado en términos de la distribución de nodos en sus diferentes niveles.

### TERCERA PARTE - 20 puntos, 10 puntos c/u

Describe el funcionamiento del siguiente algoritmo y su complejidad en términos de O(f(𝑛)).

```java
int[] mistery(int arr[]) {
  PriorityQueue<Integer> minHeap = new PriorityQueue<>()
  for (int i = 0; i < arr.length; i++){
    minHeap.add(arr[i]);
  }

  int[] arr2 = new int[arr.length];
  int j = 0;
  while (!minHeap.isEmpty()){
    arr2{j} = minHeap.poll()
    j++;
  }
  return arr2;
}
```

#### SOLUCIÓN:

El algoritmo mystery toma un arreglo de enteros arr como entrada y devuelve un nuevo arreglo arr2 que contiene los elementos de arr ordenados de menor a mayor.

La inserción de cada elemento en el min-heap toma un tiempo promedio de O(log n), donde n es el número de elementos en el min-heap. En este caso, se insertan n elementos, por lo que la complejidad total para insertar todos los elementos es O(n log n).

La extracción de cada elemento del min-heap toma un tiempo promedio de O(log n). En este caso, se extraen n elementos, por lo que la complejidad total para extraer todos los elementos es O(n log n).

O(n log n), ya que las dos operaciones principales (inserción y extracción de elementos del min-heap) tienen la misma complejidad de O(log n) y se realizan n veces cada una.
