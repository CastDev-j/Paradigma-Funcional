# Guía de Estilo para Documentación Técnica

<!-- # Paleta de Colores -->

- **Color de Texto Principal:** #333333 (un gris oscuro, fácil de leer en pantalla).
- **Color de Fondos de Bloques de Código:** #f4f4f4 (gris claro, ideal para resaltar código).
- **Color de Anotaciones y Comentarios:** #007ACC (azul, llamativo pero no intrusivo).
- **Color de Puntos Importantes/Resaltados:** #E53935 (rojo, para destacar advertencias o puntos cruciales).
- **Color para Ejemplos y Citas:** #388E3C (verde, para ilustraciones y referencias).

---

<!-- ## Uso de Colores en Markdown -->

En Markdown, puedes usar HTML dentro de los archivos para aplicar estilos personalizados. A continuación, te muestro cómo podrías aplicarlos:

---

<!-- # Guía de Programación Funcional -->

## <span style="color:#E53935;">¡Atención!</span>

Algunos conceptos clave en la programación funcional son inmutabilidad, funciones puras y composición de funciones.

---

<!-- Ejemplo de Código -->

```javascript
// Este es un comentario en el código
const add = (a, b) => a + b;
```

---

<!-- Citas y Ejemplos -->

"La programación funcional es sobre la creación de programas robustos y predecibles" - Autor desconocido

Anotaciones Importantes
<span style="color:#E53935;">Consejo:</span> Siempre intenta mantener tus funciones puras para evitar efectos secundarios indeseados.

---

<!-- ## Elementos Markdown para Documentos de Guía -->

Markdown es muy versátil. Aquí tienes una lista de elementos que puedes usar para enriquecer tu documento:

1.**Títulos y Subtítulos**:

   ```
   # Título Principal
   ## Subtítulo de Sección
   ### Subtítulo de Apartado
   ```

   # Título Principal
   ## Subtítulo de Sección
   ### Subtítulo de Apartado



2.**Listas Ordenadas y Desordenadas**:

```
- Punto de una lista desordenada
  - Subpunto
1. Punto de una lista ordenada
2. Siguiente punto
```

- Punto de una lista desordenada
  - Subpunto
1. Punto de una lista ordenada
2. Siguiente punto



3.-**Bloques de Código:**

```javascript
const sum = (a, b) => a + b;
```

const sum = (a, b) => a + b;



4.-**Citas:**

```
> "Esto es una cita de un autor."

> Tablas:

| Función  | Descripción                                     |
| -------- | ----------------------------------------------  |
| `map`    | Aplica una función a cada elemento de una lista |
| `reduce` | Reduce una lista a un solo valor                |



<table>
  <tr>
    <th>Función</th>
    <th>Descripción</th>
  </tr>
  <tr>
    <td><code>map</code></td>
    <td>Aplica una función a cada elemento de una lista.</td>
  </tr>
  <tr>
    <td><code>reduce</code></td>
    <td>Reduce una lista a un solo valor.</td>
  </tr>
  <tr>
    <td><code>filter</code></td>
    <td>Filtra los elementos de una lista según un criterio.</td>
  </tr>
  <tr>
    <td><code>flatMap</code></td>
    <td>Mapea y aplana una lista de listas en una sola lista.</td>
  </tr>
  <tr>
    <td><code>fold</code></td>
    <td>Acumula un valor a través de una lista utilizando una función.</td>
  </tr>
</table>
```
> "Esto es una cita de un autor."

> Tablas:

| Función  | Descripción                                     |
| -------- | ----------------------------------------------  |
| `map`    | Aplica una función a cada elemento de una lista |
| `reduce` | Reduce una lista a un solo valor                |


<table>
  <tr>
    <th>Función</th>
    <th>Descripción</th>
  </tr>
  <tr>
    <td><code>map</code></td>
    <td>Aplica una función a cada elemento de una lista.</td>
  </tr>
  <tr>
    <td><code>reduce</code></td>
    <td>Reduce una lista a un solo valor.</td>
  </tr>
  <tr>
    <td><code>filter</code></td>
    <td>Filtra los elementos de una lista según un criterio.</td>
  </tr>
  <tr>
    <td><code>flatMap</code></td>
    <td>Mapea y aplana una lista de listas en una sola lista.</td>
  </tr>
  <tr>
    <td><code>fold</code></td>
    <td>Acumula un valor a través de una lista utilizando una función.</td>
  </tr>
</table>




5.- **Enlaces:**

```
[Texto del enlace](https://example.com)
Imágenes:

markdown
Copiar código
![Alt text](ruta/imagen.jpg)
```

[Texto del enlace](https://example.com)
Imágenes:

markdown
Copiar código
![Alt text](ruta/imagen.jpg)



6.-**Enlaces a Secciones:**

```
[Ir a la sección de inmutabilidad](#inmutabilidad)
```

[Ir a la sección de inmutabilidad](#inmutabilidad)



7.-**Resaltar Texto:**
    
```
**Texto en negrita**
_Texto en cursiva_
```
**Texto en negrita**
_Texto en cursiva_



8.-**Checkboxes (listas de tareas):**
    
    ```
- [x] Tarea completada
- [ ] Tarea pendiente
          ```
- [ ] Tarea completada
- [ ] Tarea pendiente



9.-**Divisores:**

```
---
```

---



10.-**Notas al Pie:**

```
Este es un ejemplo con una referencia[^1].

[^1]:
    Este es el texto del footnote.
    Aplicación de Estilos en Markdown
    Recuerda que puedes mezclar Markdown con HTML para aplicar estilos específicos. Esto te permitirá personalizar la apariencia de tu guía de manera más precisa.
```

Este es un ejemplo con una referencia[^1].

[^1]:
    Este es el texto del footnote.
    Aplicación de Estilos en Markdown
    Recuerda que puedes mezclar Markdown con HTML para aplicar estilos específicos. Esto te permitirá personalizar la apariencia de tu guía de manera más precisa.



