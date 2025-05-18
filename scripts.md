CREATE TABLE categoria (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(45),
    descripcion VARCHAR(45),
    createdAt DATETIME,
    updatedAt DATETIME
);

CREATE TABLE producto (
    id INT AUTO_INCREMENT PRIMARY KEY,
    categoria_id INT,
    nombre VARCHAR(45),
    precio DOUBLE,
    cantidad INT,
    createdAt DATETIME,
    updatedAt DATETIME,
    INDEX idx_categoria_id (categoria_id),
    FOREIGN KEY (categoria_id) REFERENCES categoria(id)
);

CREATE TABLE cliente (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(45),
    apellido VARCHAR(45),
    gmail VARCHAR(45),
    telefono VARCHAR(45),
    createdAt DATETIME,
    updatedAt DATETIME
);

CREATE TABLE empleado (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(45),
    apellido VARCHAR(45),
    cargo VARCHAR(45),
    salario VARCHAR(45),
    createdAt DATETIME
);

CREATE TABLE detalle_venta (
    id INT AUTO_INCREMENT PRIMARY KEY,
    producto_id INT,
    cantidad INT,
    precio_unitario DOUBLE,
    createdAt DATETIME,
    updatedAt DATETIME,
    INDEX idx_producto_id (producto_id),
    FOREIGN KEY (producto_id) REFERENCES producto(id)
);

CREATE TABLE venta (
    id INT AUTO_INCREMENT PRIMARY KEY,
    detalle_venta_id INT,
    cliente_id INT,
    empleado_id INT,
    num_venta VARCHAR(45),
    metodo_pago VARCHAR(45),
    createdAt DATETIME,
    updatedAt DATETIME,
    INDEX idx_detalle_venta_id (detalle_venta_id),
    INDEX idx_cliente_id (cliente_id),
    INDEX idx_empleado_id (empleado_id),
    FOREIGN KEY (detalle_venta_id) REFERENCES detalle_venta(id),
    FOREIGN KEY (cliente_id) REFERENCES cliente(id),
    FOREIGN KEY (empleado_id) REFERENCES empleado(id)
);

CREATE TABLE ventacol (
    id INT AUTO_INCREMENT PRIMARY KEY,
    ventacol VARCHAR(45),
    detalle_venta_id1 INT,
    updatedAt DATETIME,
    INDEX idx_detalle_venta_id1 (detalle_venta_id1),
    FOREIGN KEY (detalle_venta_id1) REFERENCES detalle_venta(id)
);
