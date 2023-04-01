https://www.db-fiddle.com/f/5tduSFAXQ6h5CWPCmwFag7/1


CREATE DATABASE EscuelaTrigger;
USE EscuelaTrigger;

CREATE TABLE alumnos(
	Id_alumno INT UNSIGNED PRIMARY KEY,
  	Nombre_alumno VARCHAR(50),
  	Apellido1_alumno VARCHAR(50),
  	Apeliido2_alumno VARCHAR(50),
  	Nota_alumno FLOAT
	);

CREATE TABLE registro(
	Id_regristo INT AUTO_INCREMENT PRIMARY KEY,
  	Accion VARCHAR (200),
  	Fecha TIMESTAMP DEFAULT CURRENT_TIMESTAMP
	);
    

DELIMITER //

CREATE TRIGGER tg_check_nota_before_insert BEFORE INSERT ON alumnos
FOR EACH ROW BEGIN

IF NEW.Nota_alumno < 0 THEN
 SET NEW.Nota_alumno = 0;

 ELSEIF NEW.Nota_alumno > 10 THEN
 SET NEW.Nota_alumno = 10;
 /*Acaba el IF*/
 END IF;

INSERT INTO registro(Accion) VALUES (concat('Se agregó alumno con la nota de :', NEW.Nota_alumno));
END//
DELIMITER ;

INSERT INTO alumnos VALUES (1,"Manuel", "Gonzlalez", "Angeles", -2);
INSERT INTO alumnos VALUES (2, "Pedro", "Santos", "Brito", 12);
INSERT INTO alumnos VALUES (3, "Jorge", "Sanchez", "Tron", 6.5);
INSERT INTO alumnos VALUES (4,"Alejandro","Zamora","Zamudio",-10);



/*Trigger 2 lo mismo pero en una actualización no en un insert*/

DELIMITER //

CREATE TRIGGER tg_check_nota_before_update BEFORE UPDATE ON alumnos
FOR EACH ROW BEGIN

IF NEW.Nota_alumno < 0 THEN
 SET NEW.Nota_alumno = 0;

 ELSEIF NEW.Nota_alumno > 10 THEN
 SET NEW.Nota_alumno = 10;
 /*Acaba el IF*/
 END IF;

INSERT INTO registro(Accion) VALUES (concat('Se modificó alumno con la nota de :', NEW.Nota_alumno));
END//
DELIMITER ;

UPDATE alumnos set Nota_alumno = 6 where Id_alumno = -2;



![image](https://user-images.githubusercontent.com/61428623/229319279-c9c65a5c-b03b-4920-84fc-d8f9b43e420e.png)

[Ejercicio 8 Disparadores.txt](https://github.com/Armando573/Base_de_Datos/files/11130745/Ejercicio.8.Disparadores.txt)


