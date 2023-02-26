Se desea diseñar una base de datos para almacenar y gestionar la información empleada por una empresa dedicada a la venta de automóviles,
teniendo en cuenta los siguientes aspectos: La empresa dispone de una serie de coches para su venta. Se necesita conocer la matrícula, 
marca y modelo, el color y el precio de venta de cada coche. Los datos que interesa conocer de cada cliente son el NIF, nombre, dirección, 
ciudad y número de teléfono: además, los clientes se diferencian por un código interno de la empresa que se incrementa automáticamente cuando 
un cliente se da de alta en ella. Un cliente puede comprar tantos coches como desee a la empresa. Un coche determinado solo puede ser comprado 
por un único cliente. El concesionario también se encarga de llevar a cabo las revisiones que se realizan a cada coche. Cada revisión tiene asociado 
un código que se incrementa automáticamente por cada revisión que se haga. De cada revisión se desea saber si se ha hecho cambio de filtro, si se ha hecho 
cambio de aceite, si se ha hecho cambio de frenos u otros. Los coches pueden pasar varias revisiones en el concesionario


![image](https://user-images.githubusercontent.com/61428623/221386328-b62f02b7-d59a-42aa-a72f-a4f43a361dd8.png)


*****PENDIENTE POR TERMINAR******
/* Crea la tabla */
CREATE DATABASE ventas; 

/* Indica que BD se utilizara */
USE ventas; 



/* Crea la tabla */
CREATE TABLE cliente (  
  id_cliente int PRIMARY KEY,
  direccion varchar (50) NOT NULL,
  ciudad varchar (30) not null,
  nif varchar (10),
  numero_telefono char (10)
                    );



/* Crea la tabla */
CREATE TABLE concesionario (  
  id_revision varchar (6) PRIMARY KEY,
  cambio_aceite varchar (20) NOT NULL,
  cambio_filtro int,
  cambio_frenos int unsigned,
  otros varchar (20)
                    );



/* Crea la tabla */
CREATE TABLE autos (  
  id_matricula varchar (6) PRIMARY KEY,
  marca varchar (20) NOT NULL,
  modelo int,
  precio int unsigned,
  color varchar (20)
                    );





/* CREAMOS TABLAS CON DEPENDENCIAS*/
/* Crea la tabla */
CREATE TABLE autos (  
  id_matricula varchar (6) PRIMARY KEY,
  marca varchar (20) NOT NULL,
  modelo int,
  precio int unsigned,
  color varchar (20)
  /* se declara el atributo*/
  dni1 INT,
  codigo_provincia1 varchar (10),
  /* Referencia a donde es clave primaria*/
  FOREIGN KEY (dni1) REFERENCES camionero(dni),
  FOREIGN KEY (codigo_provincia1) REFERENCES provincia(codigo_provincia)
                    );
                    

/* Creamos la tabla intermedia */
CREATE TABLE cliente_consesionario (  
  dni2 int,
  matricula1 varchar (6),
  FOREIGN KEY (dni2) REFERENCES camionero (dni),
  FOREIGN KEY (matricula1) REFERENCES camion(matricula)
  );
  

