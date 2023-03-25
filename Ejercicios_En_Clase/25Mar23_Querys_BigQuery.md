SELECT * FROM `Poblacion_CDMX.Poblacion` WHERE alcaldia = 'AZCAPOTZALCO' and sexo = "Hombre";

SELECT SUM(POBLACION) AS Poblacion_Total_Azcapotzalco FROM `Poblacion_CDMX.Poblacion` WHERE alcaldia = 'AZCAPOTZALCO';


SELECT  alcaldia, poblacion, rango_edad, sexo FROM `Poblacion_CDMX.Poblacion` where rango_edad = 'e) 20 a 24 años' and poblacion > 20000 and sexo = 'Mujer';

SELECT alcaldia, sum(poblacion) AS TOTAL_Habitantes from `Poblacion_CDMX.Poblacion` group by(alcaldia) order by(sum(poblacion)) DESC ;
