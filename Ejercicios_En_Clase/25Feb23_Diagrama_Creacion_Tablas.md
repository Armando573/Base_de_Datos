/* Crea la tabla */
CREATE DATABASE Logistica; 

/* Indica que BD se utilizara */
USE Logistica; 



/* Crea la tabla */
CREATE TABLE camion (  
  matricula varchar (6) PRIMARY KEY,
  modelo int NOT NULL,
  tipo_camion varchar (20),
  potencia varchar (20)
                    );


/* Crea la tabla */
CREATE TABLE camionero (  
  dni int PRIMARY KEY,
  nombre_camionero varchar (30) NOT NULL,
  salario int unsigned,
  telefono_camionero char (10),
  poblacion_camionero varchar (20),
  direccion_camionero varchar (50)
                    );
                    
                    
/* Crea la tabla */
CREATE TABLE provincia (  
  codigo_provincia varchar (10) PRIMARY KEY,
  nombre_provincia varchar (20) NOT NULL
                    );



/* CREAMOS TABLAS CON DEPENDENCIAS*/
/* Crea la tabla */
CREATE TABLE paquetes (  
  codigo_paquete int PRIMARY KEY,
  descripcion_paquete varchar (100),
  destino_paquete varchar (20) NOT NULL,
  /* se declara el atributo*/
  dni1 INT,
  codigo_provincia1 varchar (10),
  /* Referencia a donde es clave primaria*/
  FOREIGN KEY (dni1) REFERENCES camionero(dni),
  FOREIGN KEY (codigo_provincia1) REFERENCES provincia(codigo_provincia)
                    );
                    

                
