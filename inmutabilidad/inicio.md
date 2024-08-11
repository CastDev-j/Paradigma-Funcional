# <span style="color:#333333;" id="inicio">Inmutabilidad en Programación Funcional</span>

#### <span style="color:#333333;">Sección Introducción:</span> [Introducción](../Introduccion.md)

## <span style="color:#333333;">Índice</span>

1. [Definición de Inmutabilidad](#definición-de-inmutabilidad)
2. [Ventajas de la Inmutabilidad](#ventajas-de-la-inmutabilidad)
3. [Implementación de Inmutabilidad](#implementación-de-inmutabilidad)
4. [Inmutabilidad en Diferentes Lenguajes](#inmutabilidad-en-diferentes-lenguajes)
5. [Patrones Comunes Asociados a la Inmutabilidad](#patrones-comunes-asociados-a-la-inmutabilidad)
6. [Casos Prácticos y Ejemplos](#casos-prácticos-y-ejemplos)
7. [Desventajas y Desafíos](#desventajas-y-desafíos)
8. [Herramientas y Librerías](#herramientas-y-librerías)
9. [Buenas Prácticas](#buenas-prácticas)
10. [Conclusiones y Reflexiones Finales](#conclusiones-y-reflexiones-finales)

---

## <span style="color:#333333;" id="definición-de-inmutabilidad">1. Definición de Inmutabilidad</span>

- **¿Qué es la inmutabilidad?**:
  <br>
  <p style="color:#333333;">
  La inmutabilidad significa que una vez que se ha creado un dato, no puede ser modificado. En lugar de cambiar el estado de un objeto o variable, se crean nuevos objetos con los estados actualizados. Esto ayuda a evitar efectos secundarios no deseados y facilita el desarrollo de software más predecible y confiable.
  </p>
  <h6 style="color:#388E3C;">Ejemplo en JavaScript:</h6>


```javascript
// Ejemplo de inmutabilidad en JavaScript
const person = { name: "John", age: 30 };

// En lugar de modificar directamente el objeto, creamos uno nuevo
const updatedPerson = { ...person, age: 31 };

console.log(person); // { name: 'John', age: 30 }
console.log(updatedPerson); // { name: 'John', age: 31 }
```

<br>

- **Comparación con mutabilidad**:
  <br>
  <p style="color:#333333;">
  Los objetos mutables pueden ser modificados después de su creación, lo que significa que su estado interno puede cambiar con el tiempo. Por otro lado, los objetos inmutables no pueden ser alterados una vez creados; cualquier cambio en un objeto inmutable resulta en la creación de un nuevo objeto con el nuevo estado. 
  <span style="color:#E53935;">Esta diferencia fundamental tiene implicaciones significativas en el desarrollo de software, especialmente en términos de previsibilidad, seguridad y eficiencia.</span>
  </p>
  <br>

  <span style="color:#388E3C;">Ejemplo en JavaScript:</span>

```javascript
// Ejemplo de mutabilidad en JavaScript
let mutablePerson = { name: "Alice", age: 22 };

// Modificamos directamente el objeto
mutablePerson.age = 23;

console.log(mutablePerson); // { name: 'Alice', age: 23 }
```

<br>

## <span style="color:#333333;" id="ventajas-de-la-inmutabilidad">2. Ventajas de la Inmutabilidad</span>

- <span style="color:#E53935;"><strong>Seguridad en la concurrencia</strong></span>:  
  <span style="color:#333333;">La inmutabilidad facilita el trabajo con múltiples hilos porque los objetos inmutables no pueden ser modificados una vez creados. <span style="color:#E53935;">Esto significa que no hay riesgo de condiciones de carrera, ya que los hilos no compiten por modificar el mismo objeto.</span> Al trabajar con datos inmutables, no es necesario implementar complejas estrategias de sincronización, lo que simplifica el diseño del software concurrente.</span>
<br>
- <span style="color:#007ACC;"><strong>Facilidad de depuración y prueba</strong></span>:  
  <span style="color:#333333;">Los objetos inmutables son más fáciles de depurar y probar porque su estado no cambia después de su creación. Esto reduce la cantidad de errores relacionados con cambios inesperados en el estado del objeto, lo que facilita la identificación y resolución de problemas en el código. Además, <span style="color:#E53935;">la inmutabilidad permite pruebas más predecibles y confiables</span></span>
<br>
- <span style="color:#388E3C;"><strong>Predictibilidad y simplicidad</strong></span>:  
  <span style="color:#333333;">La inmutabilidad reduce la complejidad en la gestión del estado, ya que no hay necesidad de rastrear cambios en el estado de los objetos a lo largo del tiempo. Esto hace que el comportamiento del programa sea más predecible y que el código sea más fácil de entender y mantener.</span>
<br>
## <span style="color:#333333;" id="implementación-de-inmutabilidad">3. Implementación de Inmutabilidad</span>

- <span style="color:#E53935;"><strong>Estructuras de datos inmutables</strong></span>:  
  <span style="color:#333333;">Las estructuras de datos inmutables son fundamentales en la programación funcional y en otros paradigmas que valoran la previsibilidad y la seguridad. <span style="color:#E53935;">Ejemplos comunes incluyen listas, mapas y conjuntos inmutables. </span> Estas estructuras no permiten modificaciones después de su creación, lo que asegura que sus valores permanecen constantes, facilitando la concurrencia y la depuración.</span>
<br>
- <span style="color:#007ACC;"><strong>Métodos inmutables</strong></span>:  
  <span style="color:#333333;">Los métodos inmutables están diseñados para no alterar el estado interno de un objeto. En lugar de modificar el objeto actual, estos métodos devuelven un nuevo objeto con el estado actualizado. Este enfoque es crucial para mantener la inmutabilidad y permite que el código sea más fácil de entender, probar y mantener.</span>
    <br>
  <span style="color:#388E3C;">Ejemplo en JavaScript:</span>
<div style="display: flex; flex-direction: column; gap: 20px; color:#333333;">
  <div style="background-color:#f4f4f4; padding: 20px; border-radius: 5px; border-left: 4px solid #007ACC;">
    <h3 style="margin-top: 0;">Método: <code>map</code></h3>
    <p><strong>Descripción:</strong> Aplica una función a cada elemento de un arreglo y devuelve un nuevo arreglo con los resultados, sin modificar el original.</p>

```javascript

const numbers = [1, 2, 3];
const doubled = numbers.map(n => n * 2);
            
console.log(doubled); // [2, 4, 6]
```

</div>



  <div style="background-color:#f4f4f4; padding: 20px; border-radius: 5px; border-left: 4px solid #007ACC;">
    <h3 style="margin-top: 0;">Método: <code>filter</code></h3>
    <p><strong>Descripción:</strong> Crea un nuevo arreglo con todos los elementos que pasen una prueba definida, sin alterar el arreglo original.</p>
    <p><strong>Ejemplo en JavaScript:</strong></p>

```javascript

const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter(n => n % 2 === 0);

console.log(evenNumbers); // [2, 4]
```

  </div>



  <div style="background-color:#f4f4f4; padding: 20px; border-radius: 5px; border-left: 4px solid #007ACC;">
    <h3 style="margin-top: 0;">Método: <code>concat</code></h3>
    <p><strong>Descripción:</strong> Combina dos o más arreglos y devuelve un nuevo arreglo, dejando los originales intactos.</p>
    <p><strong>Ejemplo en JavaScript:</strong></p>
  
```javascript

const arr1 = [1, 2];
const arr2 = [3, 4];

const combined = arr1.concat(arr2);

console.log(combined); // [1, 2, 3, 4]
```

  </div>



  <div style="background-color:#f4f4f4; padding: 20px; border-radius: 5px; border-left: 4px solid #007ACC;">
    <h3 style="margin-top: 0;">Método: <code>slice</code></h3>
    <p><strong>Descripción:</strong> Extrae una sección de un arreglo y devuelve un nuevo arreglo sin modificar el original.</p>
    <p><strong>Ejemplo en JavaScript:</strong></p>


```javascript

const numbers = [1, 2, 3, 4, 5];
const part = numbers.slice(1, 3);

console.log(part); // [2, 3]
```

  </div>


</div>



## <span style="color:#333333;" id="inmutabilidad-en-diferentes-lenguajes">4. Inmutabilidad en Diferentes Lenguajes</span>

- **Inmutabilidad en Java**: Uso de la palabra clave `final` y librerías como `Guava` para estructuras de datos inmutables.
- **Inmutabilidad en JavaScript**: Uso de `const`, `Object.freeze()`, y librerías como `Immutable.js`.
- **Inmutabilidad en otros lenguajes funcionales**: Como Haskell o Scala, donde la inmutabilidad es un concepto central.

## <span style="color:#333333;" id="patrones-comunes-asociados-a-la-inmutabilidad">5. Patrones Comunes Asociados a la Inmutabilidad</span>

- <span style="color:#007ACC;"><strong>Paseo de la copia (Copy-on-write)</strong></span>:  
  <span style="color:#333333;">
  El patrón de "Copy-on-write" es una técnica utilizada para optimizar la gestión de la memoria cuando se trabaja con datos inmutables. <span style="color:#E53935;">En lugar de hacer una copia completa de un objeto al modificarlo, se crea una copia solo cuando es necesario cambiar el estado del objeto.</span> Este patrón es eficiente porque permite que múltiples instancias compartan la misma referencia hasta que una de ellas necesita ser modificada. Solo en ese momento se realiza la copia, lo que reduce el consumo de memoria y mejora el rendimiento.
  </span>
   <h6 style="color:#388E3C;">Ejemplo en JavaScript:</h6>
<div style="background-color:#f4f4f4; padding: 20px; border-radius: 5px; margin-top: 10px; border-left: 4px solid #007ACC;">


```javascript

let originalArray = [1, 2, 3];
let newArray = [...originalArray]; // Copy-on-write
        
newArray.push(4);

console.log(originalArray); // [1, 2, 3]
console.log(newArray); // [1, 2, 3, 4]
```

</div>
<br> 

- <span style="color:#007ACC;"><strong>Cierre (Closure)</strong></span>:  
  <span style="color:#333333;">
  En la programación funcional, un cierre (closure) es una función que recuerda el entorno en el que fue creada, incluso después de que ese entorno haya dejado de existir. <span style="color:#E53935;">Los cierres se relacionan con la inmutabilidad porque permiten capturar y mantener un estado sin necesidad de modificar variables externas.</span> Este patrón es común en lenguajes funcionales donde la inmutabilidad es una característica clave, ya que facilita la creación de funciones que son seguras y predecibles.
  </span>

    <h6 style="color:#388E3C;">Ejemplo en JavaScript:</h6>
<div style="background-color:#f4f4f4; padding: 20px; border-radius: 5px; margin-top: 10px; border-left: 4px solid #007ACC;">

```javascript

function createCounter() {
let count = 0; // Variable inmutable dentro del closure
       
return function() {
    count += 1; 
    return count;
};
}


const counter = createCounter();

console.log(counter()); // 1
console.log(counter()); // 2

const counter2 = createCounter();

console.log(counter2()); // 1
console.log(counter2()); // 2
```

</div>
<br>

## <span style="color:#333333;" id="casos-prácticos-y-ejemplos">6. Casos Prácticos y Ejemplos</span>

### **Ejemplos en Código**

Las funciones inmutables no modifican el estado original, sino que devuelven una nueva versión de los datos. A continuación se muestran ejemplos de funciones inmutables y su comparación con enfoques mutables.

- #### **Implementación de Funciones Inmutables**

    <h6 style="color:#388E3C;">Ejemplo en JavaScript:</h6>

```javascript

// Función inmutable para sumar un número a un arreglo
function addNumber(arr, num) {
    return [...arr, num];
}

const originalArray = [1, 2, 3];
const newArray = addNumber(originalArray, 4);

console.log(originalArray); // [1, 2, 3]
console.log(newArray);      // [1, 2, 3, 4]
```

<p> 
En este ejemplo, la función addNumber no modifica el originalArray, sino que crea un nuevo arreglo con el número añadido.
</p>
<br>

- #### **Ejemplo en JavaScript - Mutable:**
    <h6 style="color:#388E3C;">Ejemplo en JavaScript:</h6>

```javascript
    // Función mutable para sumar un número a un arreglo
    function addNumberMutable(arr, num) {
        arr.push(num);
        return arr;
    }

    const originalArray = [1, 2, 3];
    const modifiedArray = addNumberMutable(originalArray, 4);

    console.log(originalArray); // [1, 2, 3, 4]
    console.log(modifiedArray); // [1, 2, 3, 4]

```

<p> 
En este caso, la función addNumberMutable modifica el originalArray directamente.
</p>

### Refactorización hacia Inmutabilidad
<p>
Refactorizar código mutable para que sea inmutable puede mejorar la previsibilidad y reducir errores. Aquí hay un ejemplo de cómo convertir un código mutable en inmutable.
</p>

- #### Código Mutable:
    <h6 style="color:#388E3C;">Ejemplo en JavaScript:</h6>

```javascript
let person = { name: 'Alice', age: 25 };

function celebrateBirthday(person) {
    person.age += 1; // Modifica el objeto original
}

celebrateBirthday(person);
console.log(person); // { name: 'Alice', age: 26 }
```

<br>

- #### Código Refactorizado a Inmutable::
    <h6 style="color:#388E3C;">Ejemplo en JavaScript:</h6>

```javascript
function celebrateBirthdayImmutable(person) {
    return { ...person, age: person.age + 1 }; // Crea un nuevo objeto
}

const person = { name: 'Alice', age: 25 };
const updatedPerson = celebrateBirthdayImmutable(person);

console.log(person); // { name: 'Alice', age: 25 }
console.log(updatedPerson); // { name: 'Alice', age: 26 }
```

<br>

## <span style="color:#333333;" id="desventajas-y-desafíos">7. Desventajas y Desafíos</span>

- **Coste en rendimiento**: Cuándo la inmutabilidad puede ser menos eficiente en términos de uso de memoria y procesamiento.
- **Complejidad en ciertas situaciones**: Casos donde la inmutabilidad puede complicar el diseño del software.
<br>

## <span style="color:#333333;" id="herramientas-y-librerías">8. Herramientas y Librerías</span>

- **Librerías para estructuras inmutables**: Herramientas disponibles para manejar datos inmutables en diferentes lenguajes.
<br>

## <span style="color:#333333;" id="buenas-prácticas">9. Buenas Prácticas</span>

- **Cuándo aplicar inmutabilidad**: Directrices sobre cuándo es mejor optar por la inmutabilidad.
- **Cómo combinar inmutabilidad con otros paradigmas**: Integración con otros enfoques de diseño de software.
<br>

## <span style="color:#333333;" id="conclusiones-y-reflexiones-finales">10. Conclusiones y Reflexiones Finales</span>

- **Resumen de la importancia de la inmutabilidad**: Recapitulación de por qué es esencial en la programación funcional.
- **Reflexión sobre el equilibrio**: Cómo encontrar el equilibrio entre inmutabilidad y mutabilidad en el desarrollo de software.

<br>
<br>
<br>

#### <span style="color:#388E3C;">[Volver al Inicio](#inicio)</span>
