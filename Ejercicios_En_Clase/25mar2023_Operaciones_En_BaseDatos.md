Taller:
Número de la práctica:
Nombre:
Folio:


1.-Lista el nombre de todos los productos que hay en la tabla producto.
Use tienda_tecnología;

Select nombre from producto;


2.-Lista los nombres y los precios de todos los productos de la tabla producto.
Use tienda_tecnología;
Select nombre, precio from producto;


3.-Lista todas las columnas de la tabla producto.

Use tienda_tecnología;

Select * from producto;


4.-Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos.
Use tienda_tecnología;

Select nombre, precio, nombre_marca  from fabricante
left join producto on fabricante.id_fabricante = producto.id_fabricante1;


*******PENDIENTES**********
Subconsultas (En la cláusula WHERE)
Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER JOIN).
*****PENDIENTE 
Use tienda_tecnología;

Select nombre from producto where  nombre = (select * from fabricante where nombre_marca = "lenovo")

Devuelve todos los datos de los productos que tienen el mismo precio que el producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).
Lista el nombre del producto más caro del fabricante Lenovo.
