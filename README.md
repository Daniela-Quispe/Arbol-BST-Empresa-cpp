## Árbol BST Empresarial en C++

# Árbol Binario de Búsqueda Empresarial (BST) en C++

## Nombre del estudiante:

Quispe Nasimba Daniela Alejandra

## Nivel y Paralelo:

3 ro "B"

## Asignatura:

Estructura de Datos

## Docente:

Ing. Jose Caiza, Mg.

## Objetivo:

Implementar en C++ un Árbol Binario de Búsqueda — BST para organizar empleados de una empresa usando un código numérico como clave. 

## Descripción del problema:

Una empresa necesita registrar empleados en una estructura jerárquica usando un árbol binario de búsqueda. El BST permite almacenar información de forma ordenada, facilitando operaciones como búsqueda, inserción y recorridos.

Cada nodo del árbol representa un empleado con:

- Código
- Nombre
- Cargo

## Funcionalidades implementadas:

- Insertar empleados  
- Buscar empleados por código  
- Mostrar nodo raíz  
- Recorrido Inorden
- Recorrido Preorden  
- Recorrido Postorden  
- Calcular altura del árbol  
- Identificar nodos hoja  
- Mostrar nivel de un nodo  

## Estructura del árbol:

Ejemplo con datos ingresados:

<pre>
        50
       /  \
     30    70
    / \    / \
  20  40  60  80
</pre>

## Recorridos del árbol:

### Inorden (Izquierda - Raíz - Derecha):

20, 30, 40, 50, 60, 70, 80.

### Preorden (Raíz - Izquierda - Derecha):

50, 30, 20, 40, 70, 60, 80.

### Postorden (Izquierda - Derecha - Raíz):

20, 40, 30, 60, 80, 70, 50.

## Altura del árbol:

- Altura: 3
- Nivel raíz (50): 0
- Nivel máximo: 2

## Nodos hoja:

Los nodos hoja (sin hijos) son:

20, 40, 60, 80.

## Niveles del árbol:

- Nivel 0 → 50  
- Nivel 1 → 30, 70  
- Nivel 2 → 20, 40, 60, 80  

## Funcionamiento del programa:

El programa implementa un Árbol Binario de Búsqueda (BST) en C++ usando nodos que almacenan empleados.

### 1. Estructura del nodo:

Cada empleado se guarda en un nodo:
<pre>
struct Empleado {
    int codigo;
    string nombre;
    string cargo;
};
</pre>
Cada nodo tiene:
* datos del empleado
* puntero izquierdo
* puntero derecho
</pre>
struct Nodo {

Empleado dato;
Nodo* izquierdo;
Nodo* derecho;
};
</pre>
### 2. Inserción de empleados:

La inserción se hace comparando el código:
</pre>
if (emp.codigo < nodo->dato.codigo) {
nodo->izquierdo = insertar(nodo->izquierdo, emp);
} 
else if (emp.codigo > nodo->dato.codigo) {
nodo->derecho = insertar(nodo->derecho, emp);
}
</pre> 
menor → izquierda
mayor → derecha

### 3. Búsqueda de empleados:
</pre>
if (nodo == nullptr || nodo->dato.codigo == codigo) {
return nodo;
}
if (codigo < nodo->dato.codigo)
return buscar(nodo->izquierdo, codigo);
else
return buscar(nodo->derecho, codigo);
</pre>
     
El árbol reduce el número de comparaciones en cada paso.

### 4. Recorrido Inorden:
</pre>
inorden(nodo->izquierdo);
mostrarEmpleado(nodo);
inorden(nodo->derecho);
</pre>
Resultado: orden ascendente por código.

### 5. Recorrido Preorden:
</pre>
mostrarEmpleado(nodo);
preorden(nodo->izquierdo);
preorden(nodo->derecho);
</pre>
Resultado: Primero la raíz, luego los hijos.

### 6. Recorrido Postorden:
</pre>
postorden(nodo->izquierdo);
postorden(nodo->derecho);
mostrarEmpleado(nodo);
</pre>
Resultado: Primero hijos, al final la raíz.

### 7. Altura del árbol:
</pre>
int alturaIzq = altura(nodo->izquierdo);
int alturaDer = altura(nodo->derecho);
return 1 + max(alturaIzq, alturaDer);
</pre>
Resultado: Calcula el nivel más profundo del árbol.

### 8. Nodos hoja:
</pre>
if (nodo->izquierdo == nullptr \&\& nodo->derecho == nullptr) {
mostrarEmpleado(nodo);
}
</pre>
Resultado: Son los nodos sin hijos.

## Capturas:

Se incluyen capturas del funcionamiento del programa:

1. Menú principal:

<img width="580" height="283" alt="Menu principal" src="https://github.com/user-attachments/assets/ba31b58c-85b4-4940-9828-0144c18416a4" />

2. Inserción de empleados:

<img width="580" height="1005" alt="Insercion de empleados " src="https://github.com/user-attachments/assets/091e1f2a-e03e-42fd-8cd5-14059376edcf" />

<img width="457" height="955" alt="Insercion de empleados" src="https://github.com/user-attachments/assets/5ba9c64a-dd83-4297-a629-782a74d41cff" />

<img width="642" height="310" alt="Insercion de empleados   " src="https://github.com/user-attachments/assets/c45f5786-2595-491c-83eb-13faf58005ee" />

3. Búsqueda:

<img width="642" height="672" alt="Busqueda" src="https://github.com/user-attachments/assets/72277a2b-62cc-4f69-8ee6-a959d4a59c01" />

<img width="663" height="1015" alt="Busqueda  " src="https://github.com/user-attachments/assets/4e31ff99-e2a3-4d94-b5f3-59de691e51e0" />

<img width="553" height="670" alt="Busqueda   " src="https://github.com/user-attachments/assets/d42c0ff0-b51f-4c0d-a547-0ed5b95bceef" />

4. Raiz:

<img width="553" height="306" alt="Raiz" src="https://github.com/user-attachments/assets/705f2d33-e0b4-49d2-b50f-e53d4ddbba85" />

6. Recorridos:

<img width="679" height="880" alt="Recorridos" src="https://github.com/user-attachments/assets/8cdfd58c-dbe5-46b5-bdfe-63f7c308d1f0" />

<img width="676" height="428" alt="Recorridos  " src="https://github.com/user-attachments/assets/a79e7605-569b-4684-b4de-0c09217b9503" />

5. Altura del árbol:

<img width="676" height="295" alt="Altura" src="https://github.com/user-attachments/assets/908c2650-80eb-44d4-8226-98a3442c3506" />

6. Nodos hoja:

<img width="526" height="376" alt="Hojas" src="https://github.com/user-attachments/assets/f59efee6-ee26-4a06-b0b9-c2fc1d7cca24" />

7. Nivel de un nodo:

<img width="526" height="599" alt="Nivel de un empleado" src="https://github.com/user-attachments/assets/998261b5-ba3c-4ae2-9ed6-c32259b7f0dd" />

<img width="712" height="618" alt="Nivel de un empleado y salida" src="https://github.com/user-attachments/assets/b312c34a-cd26-4b4f-bff5-bab04689d1f6" />

## Conclusión:

El Árbol Binario de Búsqueda (BST) es una estructura que permite organizar datos jerárquicos. Permite realizar búsquedas rápidas/eficientes y mantener los datos ordenados.
