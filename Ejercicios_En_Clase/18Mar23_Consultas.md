*****LINK PARA USAR LA BASE DE DATOS*****
https://www.db-fiddle.com/f/2pAXFxasKrzymd6fKjeSKn/0


USE tienda;
/*select char_length(nom_clie) as "Numero", nom_clie from cliente;*/

/*select now();*/

/*select FORMAT (precio,2) from producto;*/

/*select * from nota;*/

Select nom_prod, nom_clie, cant from producto 
inner join nota on nota.clave_prod1 = producto.clave_prod
inner join cliente on cliente.clave_clie = nota.clave_clie1;

