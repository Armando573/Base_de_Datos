SELECT * FROM `Poblacion_CDMX.Poblacion` WHERE alcaldia = 'AZCAPOTZALCO' and sexo = "Hombre";

SELECT SUM(POBLACION) AS Poblacion_Total_Azcapotzalco FROM `Poblacion_CDMX.Poblacion` WHERE alcaldia = 'AZCAPOTZALCO';


SELECT  alcaldia, poblacion, rango_edad, sexo FROM `Poblacion_CDMX.Poblacion` where rango_edad = 'e) 20 a 24 años' and poblacion > 20000 and sexo = 'Mujer';


SELECT alcaldia, sum(poblacion) AS TOTAL_Habitantes from `Poblacion_CDMX.Poblacion` group by(alcaldia) order by(sum(poblacion)) DESC;


SELECT alcaldia, sum(poblacion) AS TOTAL_MUJERES from `Poblacion_CDMX.Poblacion` Where sexo = 'Mujer' group by(alcaldia) order by(sum(poblacion)) DESC ;


SELECT alcaldia AS Alcaldia_Con_Mayor_Poblacion, poblacion from `Poblacion_CDMX.Poblacion` where poblacion = (Select max(poblacion) from `Poblacion_CDMX.Poblacion`);



SELECT avg(POBLACION) AS Poblacion_Total FROM `Poblacion_CDMX.Poblacion` WHERE alcaldia = 'CUAUHTEMOC';



SELECT alcaldia AS Alcaldia_Con_Mayor_Poblacion FROM `Poblacion_CDMX.Poblacion` WHERE poblacion > (SELECT avg(POBLACION) AS Poblacion_Total FROM `Poblacion_CDMX.Poblacion` WHERE alcaldia = 'CUAUHTEMOC') group by(alcaldia);





![image](https://user-images.githubusercontent.com/61428623/227746165-7663c979-82ca-4010-9836-6e4664f7f88f.png)

