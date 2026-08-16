# Lección 002: Sintaxis XML y el concepto de documento bien formado

> **Módulo:** Lenguajes de Marcas y Sistemas de Gestión de Información (0373)  
> **Tecnología:** XML (Sintaxis y reglas de marcado estricto)  
> **Canal:** Código Autodidacta  

## 📚 Tratado Teórico y Pedagógico Integral

### 1. El Concepto de Documento XML "Bien Formado" (*Well-Formed*)
En la especificación oficial del W3C para XML, existe una distinción crítica entre un documento **bien formado** y un documento **válido**. Un documento XML se considera **bien formado** si cumple estrictamente con todas las reglas sintácticas del lenguaje XML, lo que le permite ser analizado y estructurado de forma jerárquica (en forma de árbol lógico DOM) por cualquier analizador o *parser* XML estándar del mundo, independientemente de que se validen sus reglas de negocio particulares.

### 2. Reglas Sintácticas Fundamentales de XML
Para que un archivo XML sea considerado bien formado, debe cumplir con las siguientes directivas obligatorias:
* **Prólogo XML obligatorio:** Debe comenzar opcionalmente con la declaración XML que indica la versión y la codificación (ej. `<?xml version="1.0" encoding="UTF-8"?>`). No debe haber ningún carácter antes de este prólogo.
* **Elemento Raíz Único:** Todo el documento XML debe estar contenido dentro de una única etiqueta padre (el elemento raíz). No pueden existir múltiples elementos al mismo nivel jerárquico superior.
* **Cierre Obligatorio de Etiquetas:** A diferencia de HTML, en XML toda etiqueta de apertura debe tener su correspondiente etiqueta de cierre (ej. `<datos>...</datos>`). Los elementos vacíos deben cerrarse explícitamente mediante la sintaxis abreviada (ej. `<br />`).
* **Sensibilidad a Mayúsculas/Minúsculas (*Case Sensitivity*):** XML distingue estrictamente entre mayúsculas y minúsculas. Las etiquetas `<Empleado>` y `<empleado>` se interpretan como elementos totalmente diferentes y no emparejarán.
* **Anidamiento Correcto:** Las etiquetas deben cerrarse en el orden inverso al de su apertura, impidiendo el solapamiento de elementos (ej. el formato `<A><B></A></B>` es inválido; debe ser obligatoriamente `<A><B></B></A>`).
* **Uso Correcto de Atributos:** Los valores de los atributos deben ir obligatoriamente entrecomillados (con comillas simples o dobles).

### 3. Consecuencias Técnicas de la No Conformidad
Los parsers XML operan bajo una política de **fallo catastrófico inmediato** (*non-forgiving parsing*). Si un parser detecta una violación a las reglas de documento bien formado, abortará el procesamiento de inmediato lanzando un error sintáctico irrecuperable, a diferencia de los navegadores web que intentan corregir silenciosamente los errores en HTML. Esto asegura que la comunicación entre sistemas sea predecible y segura.
