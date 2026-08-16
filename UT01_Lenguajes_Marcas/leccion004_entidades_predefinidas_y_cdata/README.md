# Lección 004: Entidades predefinidas y secciones CDATA en XML

> **Módulo:** Lenguajes de Marcas y Sistemas de Gestión de Información (0373)  
> **Tecnología:** XML (Entidades de escape y bloques de datos literales)  
> **Canal:** Código Autodidacta  

## 📚 Tratado Teórico y Pedagógico Integral

### 1. Caracteres Reservados y Sintaxis de Escape
En XML, ciertos caracteres especiales están reservados por la gramática interna del lenguaje para delimitar el marcado. Escribir directamente estos caracteres en el texto de un elemento (denominado *PCDATA* o *Parsed Character Data*) causa un error fatal de parseo, ya que el analizador interpreta los símbolos como parte del código estructural.
Para solventar esto, la especificación XML predefine cinco **entidades** o secuencias de escape obligatorias:
* `&lt;` reemplaza a `<` (*less than*)
* `&gt;` reemplaza a `>` (*greater than*)
* `&amp;` reemplaza a `&` (*ampersand*)
* `&quot;` reemplaza a `"` (*double quote*)
* `&apos;` reemplaza a `'` (*apostrophe / single quote*)

### 2. Bloques de Datos Literales: Secciones CDATA
Cuando un elemento debe albergar textos extensos con múltiples caracteres reservados (como fragmentos de código de programación en Java, JavaScript, consultas SQL o scripts), escapar individualmente cada carácter es tedioso e ilegible. Para estos escenarios, XML proporciona las secciones **CDATA** (*Character Data*).
* **Funcionamiento:** Todo el contenido encerrado dentro de una sección CDATA (delimitada por `<![CDATA[` al inicio y `]]>` al cierre) es ignorado sintácticamente por el parser XML. El analizador trata el bloque completo como datos de cadena literales, sin evaluar las etiquetas ni los caracteres especiales en su interior.

### 3. Restricciones y Limitaciones Críticas
1. **Anidamiento prohibido:** Las secciones CDATA no pueden anidarse bajo ningún concepto. La aparición de la cadena de cierre `]]>` dentro de una sección CDATA abortará inmediatamente el parseo, interpretándose erróneamente como el fin de la sección externa.
2. **Uso selectivo:** Las secciones CDATA no deben usarse como un pretexto para omitir el diseño de estructuras XML jerárquicas bien formadas; deben reservarse estrictamente para datos no analizables.
