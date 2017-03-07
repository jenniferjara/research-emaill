## La regla de oro en el desarrollo de emails en HTML es: si un atributo de HTML existe úsalo en vez de CSS.

### Metas 

* Código para el navegador a fin que valide el código HTML de archivo.	
``` <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional //EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> ```

* Nos da soporte para todos los caracteres Unicode del documento.
``` <meta charset="utf-8"> ```

* Se usa para que Window Phone muestre de forma correcta en la version movil. 
``` <meta http-equiv="X-UA-Compatible" content="IE=edge"> ```

* Deshabilita el auto-scale en iOS 10 mail. 
``` <meta name="x-apple-disable-message-reformatting"> ``` 

### Body y Main Table

* En el tag Body añadir los estilos padding y magin 0px para evitar espacios inesperados de los browsers.

* Usamos un tag Table que actua como el 'body' real del la estructura, se añade los siguientes atributos width de 100% y cellpd y cellsp en 0 para quitar espacios.
En las tablas se añaden atributos cellpadding = "0" y cellspacing = "0" para quitar los espacios entre las tablas.

* En la tabla un tr es igual a una fila, y un td a una columna.

* En los tags table y td se puede usar el atributo bgcolor (color de fondo).

* Para evitar el crecimiento de tamaño del texto en los dispositivos móviles, se usa ``` text-size-adjust: 100% ``` con los prefijos que creas necesarios.



### Contenido

#### Tablas 

#### Td


* Table: añadir los atributos anteriores y esta vez con un width de 600px y align center, el ancho de 600px es seguro para que el mail se muestre en casi todas las pantallas de pc.

* Para las siguientes tablas el ancho se puede manejar en porcentajes, asi se adapatará al momento de hacer el email responsive; y si se desea cambiar el ancho solo se cambiará el ancho de elemento padre.

* Tambien se añade estilos inline ``` border-collapse: collapse ``` para evitar que versiones modernas de Outlook añadan espacios entre la tabla y el border de la tabla.

* Para los colores usar los seis carácteres del código hexagesimal.

* Cuando se utiliza padding en email, debe especificar cada uno de sus valores, de esta forma 'padding: 10px 3px 10px 4px;' o en su forma larga.

* Tener en cuenta que es seguro usar padding en los tag td, los tags como div o p se comportan de diferente manera.

* Como en las tablas el margin no funciona, se crea celdas vacias para crear estos margenes: 
  ``` <tr><td style="font-size: 0; line-height: 0;" height="10">&nbsp;</td></tr> ```

* En caso de las etiquetas de enlace, se puede cambiar de color con estilos inline o con la etiqueta font:
  ``` <a href="#" style="color: #ffffff;"><font color="ffffff">link</font></a> ```

#### Imagenes

* Imagenes como links: para quitar el borde azul típico de los links, se añade a la imagen los atributos ``` border="0" ``` y ``` display="block" ``` .

* En las imagenes es mejor mantenerlas los mas ligeras posibles, debajo de los 100kb es ideal, pero tambien debajo de los 255kb es lo standard.

### Según tipos de clientes de mail

#### Yahoo

* En Yahoo mail a los tags ``` center ``` se añade una clase por default, que tiene un ``` text-align: center, ``` y que hace que los elementos se alinien a la izquierda, para corregir se puede poner estilos inline con lo siguiente: ``` text-align:-webkit-center; ``` o  tambbien añadir a la tabla que este dentro del tag center, ``` display: inline-block; ``` .

#### Outlook

* Para evitar que Outlook añada espacio entre las tablas usar ``` mso-table-lspace: 0pt !important; mso-table-rspace: 0pt !impotant; ``` .

### Móvil 


