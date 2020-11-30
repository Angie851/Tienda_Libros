
CREATE DATABASE Libreria;

USE Libreria;

CREATE TABLE tipo_usuario(
id INT AUTO_INCREMENT,
nombre VARCHAR(30),

PRIMARY KEY (id)
);

CREATE TABLE usuarios(
id INT AUTO_INCREMENT,
usuario VARCHAR(30),
password VARCHAR(30),
nombre VARCHAR(30),
rut VARCHAR(10),
id_tipo INT,


PRIMARY KEY (id),
FOREIGN KEY (id_tipo) REFERENCES tipo_usuario(id)
);

CREATE TABLE pais (
    id INT AUTO_INCREMENT,
    nombre VARCHAR(10),
    PRIMARY KEY (id),
);

CREATE TABLE proveedor (
    id INT AUTO_INCREMENT,
    nombre_de_editorial VARCHAR(50),
    telefono VARCHAR(30),
    pais_id_fk INT,
    direccion VARCHAR(100),
    email VARCHAR(30),
    PRIMARY KEY (id),
    FOREIGN KEY (pais_id_fk) REFERENCES pais (id),
);

CREATE TABLE libro (
    id INT AUTO_INCREMENT,
    titulo VARCHAR(30),
    autor VARCHAR(30)
    stock_inicial INT,
    proveedor_id_fk INT,
    precio INT,
    PRIMARY KEY (id),
    FOREIGN KEY (proveedor_id_fk) REFERENCES proveedor (id),
);

INSERT INTO tipo_usuario VALUES (1, "ADMINISTRADOR");
INSERT INTO tipo_usuario VALUES (2, "USUARIO");

INSERT INTO Usuarios VALUES (1, "admin", "1234", "angie", "267165629", 1);
