## Árbol BST Empresarial en C++



\# Árbol Binario de Búsqueda Empresarial (BST) en C++



\---



\## Nombre del estudiante:

Quispe Nasimba Daniela Alejandra



\---



\## Nivel y Paralelo:

3 ro "B"



\---



\## Asignatura:

Estructura de Datos



\---



\## Docente:

Ing. Jose Caiza, Mg.



\---



\## Objetivo:



Implementar en C++ un Árbol Binario de Búsqueda — BST para organizar empleados de una empresa usando un código numérico como clave. 



\---



\## Descripción del problema:



Una empresa necesita registrar empleados en una estructura jerárquica usando un árbol binario de búsqueda. El BST permite almacenar información de forma ordenada, facilitando operaciones como búsqueda, inserción y recorridos.



Cada nodo del árbol representa un empleado con:



\- Código

\- Nombre

\- Cargo



\---



\## Funcionalidades implementadas:



\- Insertar empleados  

\- Buscar empleados por código  

\- Mostrar nodo raíz  

\- Recorrido Inorden

\- Recorrido Preorden  

\- Recorrido Postorden  

\- Calcular altura del árbol  

\- Identificar nodos hoja  

\- Mostrar nivel de un nodo  



\---



\## Estructura del árbol:



Ejemplo con datos ingresados:



&#x20;    50

&#x20;   /  \\

&#x20; 30    70

&#x20;/ \\    / \\

20 40  60 80



\---



\## Recorridos del árbol:



\### Inorden (Izquierda - Raíz - Derecha):



20, 30, 40, 50, 60, 70, 80.



\---



\### Preorden (Raíz - Izquierda - Derecha):



50, 30, 20, 40, 70, 60, 80.



\---





\### Postorden (Izquierda - Derecha - Raíz):



20, 40, 30, 60, 80, 70, 50.



\---



\## Altura del árbol:



\- Altura: \*\*3\*\*

\- Nivel raíz (50): \*\*0\*\*

\- Nivel máximo: \*\*2\*\*



\---



\## Nodos hoja:



Los nodos hoja (sin hijos) son:

20, 40, 60, 80.



\---



\## Niveles del árbol:



\- Nivel 0 → 50  

\- Nivel 1 → 30, 70  

\- Nivel 2 → 20, 40, 60, 80  



\---



\## Funcionamiento del programa:



El programa implementa un Árbol Binario de Búsqueda (BST) en C++ usando nodos que almacenan empleados.



\---



\### 1. Estructura del nodo:



Cada empleado se guarda en un nodo:



```cpp id="node-struct"

struct Empleado {

&#x20;   int codigo;

&#x20;   string nombre;

&#x20;   string cargo;

};



\---



Cada nodo tiene:



* datos del empleado
* puntero izquierdo
* puntero derecho



struct Nodo {

&#x20;   Empleado dato;

&#x20;   Nodo\* izquierdo;

&#x20;   Nodo\* derecho;

};



\---



\### 2. Inserción de empleados:



La inserción se hace comparando el código:



if (emp.codigo < nodo->dato.codigo) {

&#x20;   nodo->izquierdo = insertar(nodo->izquierdo, emp);

} 

else if (emp.codigo > nodo->dato.codigo) {

&#x20;   nodo->derecho = insertar(nodo->derecho, emp);

}



menor → izquierda

mayor → derecha



\---



\### 3. Búsqueda de empleados:



if (nodo == nullptr || nodo->dato.codigo == codigo) {

&#x20;   return nodo;

}



if (codigo < nodo->dato.codigo)

&#x20;   return buscar(nodo->izquierdo, codigo);

else

&#x20;   return buscar(nodo->derecho, codigo);



El árbol reduce el número de comparaciones en cada paso.



\---



\### 4. Recorrido Inorden:



inorden(nodo->izquierdo);

mostrarEmpleado(nodo);

inorden(nodo->derecho);



Resultado: orden ascendente por código.



\---



\### 5. Recorrido Preorden:



mostrarEmpleado(nodo);

preorden(nodo->izquierdo);

preorden(nodo->derecho);



Resultado: Primero la raíz, luego los hijos.



\--- 



\### 6. Recorrido Postorden:



postorden(nodo->izquierdo);

postorden(nodo->derecho);

mostrarEmpleado(nodo);



Resultado: Primero hijos, al final la raíz.



\---



\### 7. Altura del árbol:



int alturaIzq = altura(nodo->izquierdo);

int alturaDer = altura(nodo->derecho);



return 1 + max(alturaIzq, alturaDer);



Resultado: Calcula el nivel más profundo del árbol.



\---



\### 8. Nodos hoja:



if (nodo->izquierdo == nullptr \&\& nodo->derecho == nullptr) {

&#x20;   mostrarEmpleado(nodo);

}



Resultado: Son los nodos sin hijos.



\---



\## Capturas:



Se incluyen capturas del funcionamiento del programa:



1. Menú principal

2\. Inserción de empleados

3\. Búsqueda

4\. Recorridos

5\. Altura del árbol

6\. Nodos hoja

7\. Nivel de un nodo



\---



\## Conclusión:



El Árbol Binario de Búsqueda (BST) es una estructura que permite organizar datos jerárquicos. Permite realizar búsquedas rápidas/eficientes y mantener los datos ordenados.



\---





