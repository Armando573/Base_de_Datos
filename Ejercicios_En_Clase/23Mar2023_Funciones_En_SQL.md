https://www.db-fiddle.com/f/5vEtkpWmk2Ze2MaQLpMXDW/1



Use tienda_tecnología;

/* 1.- Calcula el número total de productos que hay en la tabla productos. */
Select Count (*) from producto;


/*2.- Muestra el número total de productos que tiene cada uno de los fabricantes. 
El listado también debe incluir los fabricantes que no tienen ningún producto. 
El resultado mostrará dos columnas, una con el nombre del fabricante y otra con el número de productos que tiene.Ordene el resultado descendentemente por el número de productos.*/
Select 
  nombre_marca, count(codigo_producto) from fabricante
left join producto on fabricante.id_fabricante = producto.id_fabricante1
group by (nombre_marca) order by (count (codigo_producto)) DESC; */



/*3.-Muestra el precio máximo, precio mínimo y precio medio de los productos de cada uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los datos que se solicitan.*/
Select nombre_marca, max(precio), min(precio), avg(precio)
  from producto inner join fabricante on fabricante.id_fabricante = producto.id_fabricante1
group by (nombre_marca) ;



/*4.-Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo, precio medio y el número total de productos de los fabricantes que tienen un precio medio superior a 200€. Es necesario mostrar el nombre del fabricante.   */

Select nombre_marca, max(precio), min(precio), avg(precio), count(codigo_producto)
  from producto inner join fabricante on fabricante.id_fabricante = producto.id_fabricante1
group by (nombre_marca) 
having avg (precio) > 200;

![image](https://user-images.githubusercontent.com/61428623/227748528-94215fe1-3ba1-4aeb-9732-827ba3d16fdf.png)

[Ejercicio 7 SQL.txt](https://github.com/Armando573/Base_de_Datos/files/11070476/Ejercicio.7.SQL.txt)


