https://www.db-fiddle.com/f/5XNHBhEwoHd97aB7t9a8D2/1

CREATE DATABASE proveedores;
USE proveedores;

CREATE TABLE proveedor(
  cod_prov VARCHAR(100) PRIMARY KEY,
  nom_prov VARCHAR(100) NOT NULL,
  dir_prov VARCHAR(100),
  ciudad_prov VARCHAR(100),
  provincia_prov VARCHAR(100)
  );
  
  
  CREATE TABLE categoria(
    cod_cat VARCHAR(100) PRIMARY KEY NOT NULL,
    nom_cat VARCHAR(100)
    );
   
  CREATE TABLE pieza(
  cod_pieza VARCHAR(100) PRIMARY KEY,
  nom_pieza VARCHAR(100) NOT NULL,
  color_pieza VARCHAR(50),
  precio_pieza FLOAT UNSIGNED,
  cod_cat1 VARCHAR(100),
  FOREIGN KEY (cod_cat1) REFERENCES categoria(cod_cat)
  );
  
  
  CREATE TABLE pro_pi(
  cod_prov1 VARCHAR(100),
  cod_pieza1 VARCHAR(100),
  cantidad INT UNSIGNED,
  fecha DATE,
  FOREIGN KEY (cod_prov1) REFERENCES
  proveedor (cod_prov),
  FOREIGN KEY (cod_pieza1) REFERENCES pieza(cod_pieza) 
  );

![image](https://user-images.githubusercontent.com/61428623/229324745-ff90079f-7427-486e-a83c-efa0d199cee4.png)


[proyecto final.zip](https://github.com/Armando573/Base_de_Datos/files/11130919/proyecto.final.zip)

