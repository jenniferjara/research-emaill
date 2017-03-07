##La regla de oro en el desarrollo de emails en HTML es: si existe un atributo de HTML, úsalo en vez de CSS.

###Metas 

* Código para el navegador a fin que valide el código HTML de archivo.	
``` <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional //EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> ```

* Brinda soporte para los caracteres Unicode del documento.
``` <meta charset="utf-8"> ```

* Se usa para que Window Phone muestre de forma correcta en la version movil. 
``` <meta http-equiv="X-UA-Compatible" content="IE=edge"> ```

* Deshabilita el auto-scale en iOS 10 mail. 
``` <meta name="x-apple-disable-message-reformatting"> ``` 

###Body y Main Table

* Al tag Body añadir padding y margin de 0px para evitar espacios inesperados de los browsers.

* Usamos un tag Table que actua como el 'body' real del la estructura, se añade los siguientes atributos width de 100% y ``` cellpadding = "0" ``` y ``` cellspacing = "0" ``` para quitar espacios entre las tablas.

###Contenido

* Los elementos tr y td funciones como fila y columna; si se crea una división más, se anida una nueva tabla: table>tr>td.

####<table></table> 

* Añadir los atributos anteriores ( ``` cellpadding = "0" ``` y ``` cellspacing = "0" ``` ) esta vez con un width de 600px y align center, el ancho de 600px es seguro para que el mail se muestre en casi todas las pantallas de pc.

* En las siguientes tablas el ancho se puede manejar en porcentajes, asi se adapatará al momento de hacer el email responsive; y si se desea cambiar el ancho solo se cambiará el ancho de elemento padre.

* Cuando hay elementos de tamaños específicos dentro de una tabla, es mejor poner tamaños de ancho exactos (px).

####<td></td> 

* Para centrar el contenido usar el atributo ``` align="center" ``` .

* Para alinear verticalmente el contenido de la celda hacia arriba, usar ``` valing="top" ```. Este es un atributo HTML equivalente a verical-align en CSS.
 
* Es seguro usar padding en los tag td, los tags como div o p se comportan de manera inesperada.

* Se debe especificar cada uno de sus valores: ``` padding: 10px 3px 10px 4px; ``` o ``` padding-top:10px; padding-right:10px; padding-bottom:8px ; padding-left:5px; ``` .

* Si hay problemas con el padding (que la plataforma de envio de mail excluya los estilos CSS) crear espacios con celdas vacias: 
  ``` <tr><td style="font-size: 0; line-height: 0;" height="10">&nbsp;</td></tr> ``` , (el atributo height varia).

####Imagenes

* Añadir a las imagenes ``` display: block; ``` para evitar que algunos clientes de mail añadan espacios debajo de las imagenes.

* Mantener el tamaño lo mas ligero posible, el tamaño standard es debajo de 250kb (100kb es el tamaño ideal).

* Imagenes como links: para quitar el borde azul típico de los links, se añade a la imagen los atributos ``` border="0" ``` .

* Establecer anchos definidos en Html para que en Outlook se vean correctamente, y estilos Css para otros clientes más amigables. En CSS establecer un max-widht de 600px para Windows Phone.

####Varios

* Para los colores usar los seis carácteres del código hexagesimal.

* En los tags table y td se puede usar el atributo bgcolor (color de fondo).

* Background Image: utlizar el atributo Html Background="url" en el tag td.

* En caso de las etiquetas de enlace, se puede cambiar de color con estilos inline o con la etiqueta font:
  ``` <a href="#" style="color: #ffffff;"><font color="ffffff">link</font></a> ``` .


##Según tipos de clientes de mail

####Yahoo

* En Yahoo mail a los tags ``` center ``` se añade una clase por default, que tiene un ``` text-align: center, ``` y que hace que los elementos se alinien a la izquierda, para corregir se puede poner estilos inline con lo siguiente: ``` text-align:-webkit-center; ``` o  tambbien añadir a la tabla que este dentro del tag center, ``` display: inline-block; ``` .

* ``` Margin: 0 auto; ``` centar una tabla en Yahoo y Chrome (Margin con mayúscula). 

####Outlook

* Para evitar que Outlook añada espacio entre las tablas usar ``` mso-table-lspace: 0pt !important; mso-table-rspace: 0pt !impotant; ``` .

* Añadir a las tablas estilos inline ``` border-collapse: collapse ``` para evitar que versiones modernas de Outlook añadan espacios entre la tabla y el border de la tabla.



#### Móvil 

* Para evitar el crecimiento de tamaño del texto en los dispositivos móviles, se usa ``` text-size-adjust: 100% ``` con los prefijos que creas necesarios.

