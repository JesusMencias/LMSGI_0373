# Lección 006: Estructura en árbol y nodos en XML

> **Módulo:** Lenguajes de Marcas y Sistemas de Gestión de Información (0373)  
> **Tecnología:** XML (Modelo de objetos del documento y jerarquía de nodos)  
> **Canal:** Código Autodidacta  

## 📚 Tratado Teórico y Pedagógico Integral

### 1. El Modelo de Documento en Árbol (DOM)
A nivel lógico y en memoria, todo documento XML bien formado se representa como una estructura de datos abstracta de **árbol jerárquico invertido**. El árbol se inicia en un vértice superior único denominado **raíz del documento** y se ramifica hacia abajo a través de elementos anidados hasta alcanzar las hojas finales (compuestas fundamentalmente por nodos de texto). Esta representación formal es la base sobre la que operan los analizadores (*parsers* DOM), los motores de búsqueda de patrones (XPath / XQuery) y los lenguajes de transformación (XSLT).

### 2. Taxonomía Formal de Nodos en XML
Cada componente sintáctico dentro de un documento XML constituye un **nodo** especializado:
* **Nodo Documento (Document Node / Root Node):** Es el contenedor conceptual global que engloba todo el archivo en memoria (incluyendo el prólogo, comentarios externos y el elemento raíz).
* **Nodo Elemento (Element Node):** Bloques estructurales principales delimitados por etiquetas (`<etiqueta>...</etiqueta>`). Son los únicos nodos capaces de contener otros elementos anidados.
* **Nodo Atributo (Attribute Node):** Pares `clave="valor"` asociados a un elemento específico. **Distinción crítica:** los atributos *no* son nodos hijos del elemento, sino metadatos adscritos a dicho nodo.
* **Nodo Texto (Text Node):** Contenido textual plano (*PCDATA*) encerrado dentro de un elemento. En el árbol DOM, el texto es un nodo hijo de tipo texto subordinado al elemento que lo contiene.
* **Nodo Comentario (Comment Node):** Anotaciones para desarrolladores (`<!-- ... -->`) preservadas en el árbol DOM pero ignoradas en el procesamiento de datos de negocio.
* **Nodo Instrucción de Procesamiento (Processing Instruction Node):** Directivas específicas enviadas a las aplicaciones de procesamiento (`<?target ...?>`).

### 3. Relaciones de Parentesco Jerárquico
Para navegar y direccionar nodos de forma unívoca en el árbol XML, se definen relaciones genealógicas formales:
* **Padre (*Parent*):** El elemento contenedor inmediato de nivel superior. Todo nodo (excepto el nodo documento) tiene exactamente un único padre.
* **Hijo (*Child*):** Nodos contenidos inmediatamente un nivel por debajo de un elemento padre.
* **Hermanos (*Siblings*):** Nodos que comparten exactamente el mismo nodo padre directo (ej. `<nombre>` y `<salario>`).
* **Ancestros (*Ancestors*):** Toda la cadena de nodos superiores directos e indirectos (padre, abuelo, etc.) hasta la raíz.
* **Descendientes (*Descendants*):** Toda la jerarquía de nodos subordinados directos e indirectos (hijos, nietos, etc.).
