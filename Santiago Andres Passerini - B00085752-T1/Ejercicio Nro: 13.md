# Ejercicio Nro 13

## Enunciado
Tu tarea es desarrollar una aplicación informática utilizando la técnica TDD. Para este caso práctico, el sistema gestionará el stock de productos de una tienda. La aplicación debe permitir a los usuarios registrar un producto, agregar stock, retirar mercadería y transferir artículos entre diferentes depósitos.

Etapa 1: Especificación y prueba inicial
1. Especificación de requisitos básicos y funcionalidades clave.
2. Escribe una prueba inicial que verifique si el sistema puede crear una instancia de un producto y obtener su stock inicial.

## Resolución

### 1. Especificación de requisitos básicos y funcionalidades clave
* **Registro de producto:** Creación de una instancia de artículo asociada a un código único y un nombre, con la opción de asignar un stock inicial.
* **Ingreso de mercadería:** Incremento del stock disponible mediante el ingreso de una cantidad válida y positiva.
* **Retiro de mercadería:** Reducción del stock mediante una extracción, validando que no se supere la cantidad disponible ni se ingresen montos negativos.
* **Transferencia de stock:** Traspaso de artículos desde un depósito origen hacia un depósito destino de forma segura y atómica.

### 2. Prueba inicial (Ciclo TDD - Fase Roja)
* **Objetivo:** Validar la creación correcta de la entidad y la lectura del stock inicial asignado.
* **Código de la prueba (JavaScript):**

```javascript
const assert = require('assert');
const { ProductoInventario } = require('./productoInventario');

try {
    console.log("Ejecutando Prueba Inicial: Registro de Producto...");
    const producto = new ProductoInventario("A-001", "Teclado Mecánico", 50);
    
    assert.strictEqual(producto.codigoArticulo, "A-001");
    assert.strictEqual(producto.obtenerStock(), 50);
    console.log("✔ Prueba superada.");
} catch (error) {
    console.error("Resultado esperado: La prueba fallará inmediatamente ya que la clase 'ProductoInventario' aún no está implementada.");
    console.error(error.message);
}
```
Enunciado
Etapa 2: Desarrollo de las funcionalidades básicas
3. Implementa la funcionalidad para registrar la entidad, asegurándote de que se cumplan los requisitos especificados. Ejecuta la prueba y verifica que pase correctamente.
4. Implementa la funcionalidad para realizar ingresos de stock. Ejecuta las pruebas y verifica que pasen correctamente.
5. Implementa la funcionalidad para realizar retiros de stock. Ejecuta las pruebas y verifica que pasen correctamente.
6. Implementa la funcionalidad para transferir artículos entre depósitos. Ejecuta las pruebas y verifica que pasen correctamente.

Resolución
3. Implementación para registrar un producto (Fase Verde)
Código de la prueba (JavaScript):

```JavaScript
class ProductoInventario {
    constructor(codigoArticulo, nombre, stockInicial = 0) {
        this.codigoArticulo = codigoArticulo;
        this.nombre = nombre;
        this.stock = stockInicial >= 0 ? stockInicial : 0;
    }

    obtenerStock() {
        return this.stock;
    }
}

module.exports = { ProductoInventario };
```
Resultado: Al ejecutar la prueba inicial de la Etapa 1 con este código, el resultado pasa a Verde exitosamente.

4. Implementación para ingresar mercadería
Código de la prueba (Fase Roja):

```JavaScript
const articulo = new ProductoInventario("A-001", "Teclado Mecánico", 50);
articulo.agregarStock(20);
assert.strictEqual(articulo.obtenerStock(), 70); 
// Error: articulo.agregarStock is not a function
```
Código de producción actualizado (Fase Verde):

```JavaScript
class ProductoInventario {
    constructor(codigoArticulo, nombre, stockInicial = 0) {
        this.codigoArticulo = codigoArticulo;
        this.nombre = nombre;
        this.stock = stockInicial >= 0 ? stockInicial : 0;
    }

    obtenerStock() {
        return this.stock;
    }

    agregarStock(cantidad) {
        if (cantidad <= 0) {
            throw new Error("La cantidad a ingresar debe ser mayor a cero.");
        }
        this.stock += cantidad;
    }
}
```
5. Implementación para retirar mercadería
Código de la prueba (Fase Roja):

```JavaScript
const articulo = new ProductoInventario("A-001", "Teclado Mecánico", 70);
articulo.retirarStock(30);
assert.strictEqual(articulo.obtenerStock(), 40);
// Error: articulo.retirarStock is not a function
```
Código de producción actualizado (Fase Verde):

```JavaScript
class ProductoInventario {
    // ... constructor, obtenerStock y agregarStock se mantienen igual
    
    retirarStock(cantidad) {
        if (cantidad <= 0) {
            throw new Error("La cantidad a retirar debe ser mayor a cero.");
        }
        if (cantidad > this.stock) {
            throw new Error("Stock insuficiente.");
        }
        this.stock -= cantidad;
    }
}
```
6. Implementación para transferir stock entre depósitos
Para este requerimiento, se introduce la entidad GestorDepositos que orquestará la interacción entre múltiples ubicaciones.

Código de la prueba (Fase Roja):

```JavaScript
const { ProductoInventario, GestorDepositos } = require('./productoInventario');

const gestor = new GestorDepositos();
const depositoNorte = new ProductoInventario("DEP-1", "Depósito Norte", 100);
const depositoSur = new ProductoInventario("DEP-2", "Depósito Sur", 20);

gestor.registrarUbicacion(depositoNorte);
gestor.registrarUbicacion(depositoSur);
gestor.transferirStock("DEP-1", "DEP-2", 30);

assert.strictEqual(depositoNorte.obtenerStock(), 70);
assert.strictEqual(depositoSur.obtenerStock(), 50);
// Error: GestorDepositos is not a constructor
```
Código de producción actualizado (Fase Verde - productoInventario.js):

```JavaScript
class GestorDepositos {
    constructor() {
        this.ubicaciones = new Map();
    }

    registrarUbicacion(ubicacion) {
        this.ubicaciones.set(ubicacion.codigoArticulo, ubicacion);
    }

    transferirStock(codigoOrigen, codigoDestino, cantidad) {
        const origen = this.ubicaciones.get(codigoOrigen);
        const destino = this.ubicaciones.get(codigoDestino);

        if (!origen) throw new Error("Ubicación de origen no encontrada.");
        if (!destino) throw new Error("Ubicación de destino no encontrada.");

        origen.retirarStock(cantidad);
        destino.agregarStock(cantidad);
    }
}

module.exports = { ProductoInventario, GestorDepositos };
```
Enunciado
Etapa 3: Pruebas adicionales y mejoras
7. Escribe pruebas adicionales para cubrir casos de prueba específicos, como intentar retirar más artículos de los disponibles o transferir a un depósito inexistente.
8. Ejecuta todas las pruebas y verifica que pasen correctamente.
9. Refactoriza tu código si es necesario para mejorar su estructura, legibilidad y eficiencia.
10. Ejecuta todas las pruebas nuevamente para asegurarte de que el código refactorizado no haya introducido errores.

Resolución
7. Pruebas adicionales:
Código de las pruebas (JavaScript):

```JavaScript
const { ProductoInventario, GestorDepositos } = require('./productoInventario');
const assert = require('assert');

// Caso Excepcional A: Intentar retirar más unidades de las disponibles
const testArticulo = new ProductoInventario("X-999", "Monitor", 10);
assert.throws(() => {
    testArticulo.retirarStock(15); 
}, /Stock insuficiente/);

// Caso Excepcional B: Transferir a una ubicación que no existe en el gestor
const miGestor = new GestorDepositos();
const ubicacionOrigen = new ProductoInventario("DEP-1", "Central", 50);
miGestor.registrarUbicacion(ubicacionOrigen);

assert.throws(() => {
    miGestor.transferirStock("DEP-1", "DEP-INEXISTENTE", 10);
}, /Ubicación de destino no encontrada/);
8. Ejecución y Ajustes (Fase Verde)
Para asegurarnos de que estas validaciones pasen, el código de producción debe verificar activamente estas condiciones lanzando errores explícitos:
```
```JavaScript
// Fragmento de lógica clave
retirarStock(cantidad) {
    if (cantidad > this.stock) {
        throw new Error("Stock insuficiente.");
    }
    this.stock -= cantidad;
}

transferirStock(codigoOrigen, codigoDestino, cantidad) {
    const origen = this.ubicaciones.get(codigoOrigen);
    const destino = this.ubicaciones.get(codigoDestino);

    if (!origen) throw new Error("Ubicación de origen no encontrada.");
    if (!destino) throw new Error("Ubicación de destino no encontrada.");

    origen.retirarStock(cantidad);
    destino.agregarStock(cantidad);
}
```
9. Refactorización (Refactoring)
Problema detectado: Al revisar el código actual, notamos que tanto en agregarStock() como en retirarStock() estamos repitiendo manualmente la validación de que la cantidad sea un número positivo.

Acción de Refactor: Extraeremos la validación de cantidades negativas a un método privado interno para limpiar la estructura.

Código Refactorizado (productoInventario.js):

```JavaScript
class ProductoInventario {
    constructor(codigoArticulo, nombre, stockInicial = 0) {
        this.codigoArticulo = codigoArticulo;
        this.nombre = nombre;
        this.stock = stockInicial >= 0 ? stockInicial : 0;
    }

    obtenerStock() {
        return this.stock;
    }

    #validarCantidadPositiva(cantidad) {
        if (cantidad <= 0) {
            throw new Error("La cantidad debe ser mayor a cero.");
        }
    }

    agregarStock(cantidad) {
        this.#validarCantidadPositiva(cantidad);
        this.stock += cantidad;
    }

    retirarStock(cantidad) {
        this.#validarCantidadPositiva(cantidad);
        if (cantidad > this.stock) {
            throw new Error("Stock insuficiente.");
        }
        this.stock -= cantidad;
    }
}
```
10. Ejecución post-refactorización
Al correr la suite completa de pruebas unitarias con la nueva estructura interna, todas las pruebas pasan en verde porque la interfaz pública se mantuvo intacta.

Enunciado
Etapa 4: Cobertura completa de pruebas
11. Asegúrate de que todas las funcionalidades del sistema estén cubiertas por pruebas automatizadas.
12. Examina los casos límite y situaciones excepcionales para garantizar que el sistema se comporte correctamente en todos los escenarios.
13. Ejecuta todas las pruebas y verifica que pasen correctamente.

Recuerda seguir el enfoque TDD, donde agregarás una prueba antes de implementar cada funcionalidad y verificarás que todas las pruebas pasen antes de pasar a la siguiente etapa. Esto te ayudará a desarrollar una aplicación confiable, mantenible y que cumpla con los requisitos establecidos.

Resolución
11 y 12. Cobertura total y análisis de Casos Límite (Fase Roja)
Análisis de Frontera / Casos Límite:

Valor cero exacto: Validar que el sistema rechace movimientos de 0 unidades.

Stock vacío: Verificar qué pasa si se retira exactamente el total de los artículos y el depósito queda vacío (debería permitirlo dejando el valor en 0).

Código de pruebas para Casos Límite (JavaScript):

```JavaScript
// Caso Límite 1: Intentar ingresar cero unidades
const articuloLimite = new ProductoInventario("L-001", "Mouse", 20);
assert.throws(() => {
    articuloLimite.agregarStock(0);
}, /La cantidad debe ser mayor a cero/);

// Caso Límite 2: Retiro del total exacto (Quedar sin stock)
articuloLimite.retirarStock(20); 
assert.strictEqual(articuloLimite.obtenerStock(), 0); // Debería funcionar sin lanzar error
13. Ejecución final del sistema (Fase Verde)
Las validaciones precisas implementadas durante la refactorización superan exitosamente las pruebas de frontera.
```
Al ejecutar el set completo de pruebas integradas en la consola:

=== INICIANDO SUITE DE PRUEBAS TDD DE INVENTARIO ===
▶ Probando Etapa 1... ✔ OK
▶ Probando Etapa 2... ✔ OK
▶ Probando Etapa 3... ✔ OK
▶ Probando Etapa 4... ✔ OK
¡TODAS LAS PRUEBAS PASARON EXITOSAMENTE!
