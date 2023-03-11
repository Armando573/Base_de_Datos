 CREATE DATABASE biblioteca;
 USE biblioteca;
CREATE TABLE autores (
id_autor VARCHAR(100) PRIMARY KEY,
nombre_autor VARCHAR(100) NOT NULL
);
--Insertamos los datos
INSERT INTO autores VALUES ('aut1','Jan Márquez');
INSERT INTO autores VALUES ('aut2','Miguel Pérez');
INSERT INTO autores VALUES ('aut3','Angel Santos');
INSERT INTO autores VALUES ('aut4','Pedro Sánchez');
INSERT INTO autores VALUES ('aut5','Daniel Nieves');
INSERT INTO autores VALUES ('aut6','Adrian Luevano');
INSERT INTO autores VALUES ('aut7','Ivan Juárez');
INSERT INTO autores VALUES ('aut8','Wendy Beltran');
INSERT INTO autores VALUES ('aut9','María Urbina');

CREATE TABLE libros (
isbn INT UNSIGNED PRIMARY KEY,
editorial VARCHAR(100) NOT NULL,
año_escritura YEAR, 
titulo VARCHAR(100) NOT NULL
);
INSERT INTO libros VALUES (01,'Editorial Planeta','1998','Pan y vino');
INSERT INTO libros VALUES (02,'Editorial Editores Mexicanos','1998','Pan y vino');
INSERT INTO libros VALUES (03,'Editorial Planeta','1998','Pan y vino');
INSERT INTO libros VALUES (04,'Editorial Editanet','1998','Pan y vino');
INSERT INTO libros VALUES (05,'Editorial Editanet','1998','Pan y vino');
INSERT INTO libros VALUES (06,'Editorial Editanet','1998','Pan y vino');
INSERT INTO libros VALUES (07,'Editorial Planeta','1998','Pan y vino');
INSERT INTO libros VALUES (08,'Editorial Edimex','1998','Pan y vino');
INSERT INTO libros VALUES (09,'Editorial Planeta','1998','Pan y vino');
INSERT INTO libros VALUES (10,'Editorial Edimex','1998','Pan y vino');

CREATE TABLE personas (
dni VARCHAR(10) PRIMARY KEY,
nombre VARCHAR(50) NOT NULL,
apellidos VARCHAR(50),
direccion VARCHAR(100),
telefono BIGINT UNSIGNED
);
INSERT INTO personas VALUES (74659,'Juan Pedro','Martínez Pérez','Av del trabajo #15 colonia petrolera',5567465353);
INSERT INTO personas VALUES (76589,'Daniel',NULL,NULL,56789835);
INSERT INTO personas VALUES (878945,'Angélica','Juárez','Priv del desierto #34',554598093);
INSERT INTO personas VALUES (90867,'Adrián','López Pérez','Aquiles Serdán #34',5567873423);
INSERT INTO personas VALUES (65478,'Monserrat','Martínez Annaya','Potrero #34 colonia Américas',56784534);
INSERT INTO personas VALUES (34678,'Ángeles','Sánchez Leal','Av del Rosario #45 colonia Rosario',5576897876);
INSERT INTO personas VALUES (56749,'Juana','Domíngez Campos','Andador peten #45 colonia Roma',5678563465);
INSERT INTO personas VALUES (28490,'Andrea','Manrriquez Angulo','Av San pedro #90 colina San Pedro',5598478349);
INSERT INTO personas VALUES (47893,'Paulo','Dávila Arcos','Patriotismo #12 colonia Puerto Áereo',5545768934);
INSERT INTO personas VALUES (19840,'Armando','Martínez Hernández','Desccartes #2 colonia Centro',5545123421);

CREATE TABLE prestamos (
id_prestamo INT UNSIGNED PRIMARY KEY,
fecha_real DATE NOT NULL,
fecha_prestamo DATE NOT NULL,
dni1 VARCHAR(10),
FOREIGN KEY (dni1) REFERENCES personas(dni)
);
INSERT INTO prestamos VALUES (19,'2022-05-01','2022-03-01',74659);
INSERT INTO prestamos VALUES (31,'2022-03-12','2022-02-14',74659);
INSERT INTO prestamos VALUES (45,'2022-05-10','2021-04-13',47893);
INSERT INTO prestamos VALUES (34,'2022-05-01','2022-05-09',28490);
INSERT INTO prestamos VALUES (23,'2022-04-15','2022-04-24',19840);

CREATE TABLE volumenes (
id_volumen INT UNSIGNED PRIMARY KEY,
deteriodo VARCHAR(2) NOT NULL,
id_prestamo1 INT UNSIGNED NOT NULL,
isbn2  INT UNSIGNED NOT NULL,
FOREIGN KEY (isbn2) REFERENCES libros(isbn),
FOREIGN KEY (id_prestamo1) REFERENCES prestamos(id_prestamo)
);
INSERT INTO volumenes VALUES (09989,'no',19,01);
INSERT INTO volumenes VALUES (09990,'no',31,06);
INSERT INTO volumenes VALUES (09991,'no',45,03);
INSERT INTO volumenes VALUES (09992,'no',23,04);
INSERT INTO volumenes VALUES (09993,'no',34,05);

CREATE TABLE auto_lib (
id_autor1  VARCHAR(100) NOT NULL,
isbn1 INT UNSIGNED NOT NULL,
FOREIGN KEY (id_autor1) REFERENCES autores(id_autor),
FOREIGN KEY (isbn1) REFERENCES libros(isbn)
);
INSERT INTO auto_lib VALUES ('aut2',05);
INSERT INTO auto_lib VALUES ('aut5',03);
INSERT INTO auto_lib VALUES ('aut3',01);
INSERT INTO auto_lib VALUES ('aut1',02);
INSERT INTO auto_lib VALUES ('aut4',03);



![image](https://user-images.githubusercontent.com/61428623/224512178-9e17f772-d79e-49d6-91bf-86de7c65fec6.png)

![image](https://user-images.githubusercontent.com/61428623/224512514-6b41d18f-22a3-496a-8d0d-e3f780e8bc41.png)

![image](https://user-images.githubusercontent.com/61428623/224512821-13aa0f8d-3b93-4062-bcdd-c394b7e67214.png)

![image](https://user-images.githubusercontent.com/61428623/224514032-e8c19d34-bc4f-47f7-940a-539e70da8298.png)

