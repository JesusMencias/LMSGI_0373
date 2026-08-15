# Lección 001: ¿Qué es un lenguaje de marcas? Definición y codificación

> **Módulo:** Lenguajes de Marcas y Sistemas de Gestión de Información (0373)  
> **Tecnología:** XML (Fundamentos de marcado descriptivo)  
> **Canal:** Código Autodidacta  

## 📚 Tratado Teórico y Pedagógico Integral

### 1. Definición Formal de Lenguaje de Marcas
Un **lenguaje de marcas** (o de etiquetado) es una estructura de codificación sintáctica que combina texto plano (el contenido o dato puro) con información auxiliar (el metadato) en forma de anotaciones o marcas, con el propósito de definir la estructura, la semántica o el formato de presentación de la información. La característica fundamental de un lenguaje de marcas es que la información de marcado y el contenido del texto residen en el mismo archivo físico, pero son distinguibles lógicamente mediante reglas sintácticas estrictas.

### 2. Taxonomía de los Lenguajes de Marcas
Históricamente, los lenguajes de marcas se clasifican según su propósito en tres grandes categorías:
* **Marcado de Presentación (Presentational):** Define la apariencia visual del texto en un soporte de visualización (ej. tamaño de fuente, colores, cursivas). Ejemplos clásicos son procesadores de texto antiguos o formatos como RTF.
* **Marcado de Procedimiento (Procedural):** Indica comandos u operaciones activas que un procesador de texto o una máquina debe realizar sobre el contenido (ej. PostScript o macros de formateo de texto).
* **Marcado Descriptivo o Semántico (Descriptive):** Identifica el significado lógico de los bloques de información, independizándose por completo de cómo se representará visualmente en pantalla (ej. definir que un bloque es un `<titulo>`, un `<precio>` o una `<fecha>`). El estándar XML es el máximo exponente de esta categoría.

### 3. El Rol de la Codificación en la Interoperabilidad
Para garantizar que los archivos de datos puedan ser legibles en cualquier arquitectura informática mundial, se recurre a la **codificación de caracteres estándar** (siendo `UTF-8` el estándar global absoluto por soportar todo el espectro Unicode en longitud variable). El marcado permite que las aplicaciones de destino validen la integridad sintáctica de la estructura jerárquica jerárquica del documento, sirviendo como un contrato de datos sólido para el intercambio electrónico de información corporativa.
