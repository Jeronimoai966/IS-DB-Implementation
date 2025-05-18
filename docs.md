![diagrama_tienda](https://github.com/user-attachments/assets/f6350a6a-4718-4662-84da-f3e92b33f374) png original
![MiApellido_DDL_DB sql](https://github.com/user-attachments/assets/f9d43b93-36be-4000-a115-bf7edfc60878) png hecho por mi

# Decisiones de Diseño - Base de Datos Tienda

## 1. Separación de Tablas
Decidí crear una tabla para cada entidad principal: clientes, empleados, productos, categorías, ventas y detalles de venta. Esto lo hice porque así es más fácil organizar la información y evitar que se repita.

## 2. Llaves Primarias y Foráneas
A cada tabla le puse una columna `id` como llave primaria para identificar cada registro. Usé llaves foráneas para conectar las tablas entre sí, por ejemplo, el producto tiene una referencia a la categoría y la venta tiene referencias al cliente y al empleado.

## 3. Tipos de Datos
Elegí tipos de datos sencillos como `VARCHAR(45)` para textos cortos (nombres, correos, etc.), `INT` para números y `DOUBLE` para precios. Para las fechas, usé `DATETIME` porque así puedo saber cuándo se creó o actualizó cada registro.

## 4. Índices
Agregué índices en las columnas que son llaves foráneas para que las búsquedas sean más rápidas, aunque todavía no entiendo muy bien cómo funcionan los índices, sé que ayudan al rendimiento.

## 5. Auditoría
Incluí los campos `createdAt` y `updatedAt` en casi todas las tablas para poder saber cuándo se crearon o modificaron los datos. Esto lo vi en ejemplos y me pareció útil para el futuro.

## 6. Relaciones
Me aseguré de que las relaciones entre tablas estuvieran bien definidas usando las llaves foráneas, así si borro un registro relacionado, la base de datos me avisa si hay un problema.

---

