# Lección 003: Elementos y atributos en XML

> **Módulo:** Lenguajes de Marcas y Sistemas de Gestión de Información (0373)  
> **Tecnología:** XML (Arquitectura de datos y diseño de esquemas)  
> **Canal:** Código Autodidacta  

## 📚 Tratado Teórico y Pedagógico Integral

### 1. Elementos vs. Atributos en XML
En el modelado de datos utilizando XML, existen dos estructuras fundamentales para representar información:
* **Elementos:** Representan bloques de datos con identidad lógica propia. Comienzan con una etiqueta de apertura y terminan con una de cierre. Pueden albergar texto plano, otros subelementos jerárquicos (anidados) y atributos.
* **Atributos:** Proporcionan metadatos adicionales, propiedades o características complementarias asociadas a un elemento particular. Se declaran obligatoriamente dentro de la etiqueta de apertura del elemento en forma de pares de clave/valor (ej. `nombre="valor"`).

### 2. Criterios Arquitectónicos y Directrices de Diseño
Una de las decisiones más complejas en el diseño de esquemas XML es determinar cuándo un dato de negocio debe ser un elemento o un atributo. No existen reglas absolutas, pero sí pautas arquitectónicas recomendadas por la W3C:
* **Uso de Elementos:** Deben utilizarse para la **información de negocio central** (los datos primarios). Si un dato requiere subdivisiones lógicas (estructura interna), múltiples ocurrencias del mismo tipo, o un contenido extenso y multilínea, debe ser obligatoriamente un elemento.
* **Uso de Atributos:** Deben reservarse exclusivamente para **metadatos de control** que no forman parte de la información directa del negocio (ej. identificadores únicos de base de datos como `id="P001"`, especificaciones de codificación, idioma, unidades de medida como `moneda="EUR"` o propiedades de representación técnica).

### 3. Limitaciones Estructurales de los Atributos
Diseñar estructuras de datos abusando de los atributos acarrea severas limitaciones:
1. Los atributos no pueden contener múltiples valores directamente estructurados (no admiten subelementos).
2. No se puede controlar fácilmente su orden de aparición sintáctico.
3. No admiten fácilmente valores nulos ni estructuras repetitivas complejas.
4. Complican el mantenimiento y la extensibilidad futura del esquema XML.
