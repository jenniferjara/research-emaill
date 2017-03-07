## La regla de oro en el desarrollo de emails en HTML es: si un atributo de HTML existe úsalo en vez de CSS.

### Metas 

* Código para el navegador a fin que valide el código HTML de archivo.	

``` <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional //EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> ```

``` <meta charset="utf-8"> ```
* Nos da soporte para todos los caracteres Unicode del documento.

``` <meta http-equiv="X-UA-Compatible" content="IE=edge"> ```
* Se usa para que Window Phone muestre de forma correcta en la version movil. 

``` <meta name="x-apple-disable-message-reformatting"> ``` 
* Deshabilita el auto-scale en iOS 10 mail. 

### Body y Main Table

* Body: añadir padding y magin 0px para evitar espacios inesperados.

* Table: que actua como el 'body' real del la estructura, añadir los siguientes atributos directamente en el html, con un width de 100% y cellpd y cellsp en 0 para quitar espacios.

* En la tabla un tr es igual a una fila, y un td a una columna.

* En los tags table y td se puede usar el atributo bgcolor (color de fondo).

* Para evitar el crecimiento de tamaño del texto en los dispositivos móviles, se usa ``` text-size-adjust: 100% ``` con los prefijos que creas necesarios.

* Para evitar que Outlook añada espacio entre las tablas usar ``` mso-table-lspace: 0pt !important; mso-table-rspace: 0pt !impotant; ``` .

### Contenido

* Table: añadir los atributos anteriores y esta vez con un width de 600px y align center, es un ancho seguro para que el mail se muestre en casi todas las pantallas de pc.

* Para las siguientes tablas el ancho se puede manejar en porcentajes, asi se adapatará al momento de hacer el email responsive, si se desea cambiar el ancho solo se cambiará el ancho de elemento padre.

* Tambien se añade estilos inline ``` border-collapse: collapse ``` para evitar de versiones modernas de Outlook añadan espacios entre la tabla y el border.

* En caso de los colores, es preferente utilizar los seis carácteres del código hexagesimal.

* Cuando se utiliza padding en email, debe especificar cada uno de sus valores, de esta forma 'padding: 10px 3px 10px 4px;' o en su forma larga.

* Tener en cuenta que es seguro usar padding en los tag td. 

* Como en las tablas el margin no funciona, se usa celdas vacias para crear estos margenes: ``` <tr><td style="font-size: 0; line-height: 0;" height="10">&nbsp;</td></tr> ```

* En caso de las etiquetas de enlace, se puede cambiar de color con estilos inline o con la etiqueta font, va dentro del tag a usando el atributo html 'color' 

``` <a href="#" style="color: #ffffff;"><font color="ffffff">link</font></a> ```

* Imagenes como link: para quitar el borde azul típico de los links, se añade el atributo ``` border="0" ``` a la imagen y ``` display="block" ``` .

* En Yahoo mail a los tags ``` center ``` se añade una clase por default, que tiene un ``` text-align: center, ``` y que hace que los elementos se alinien a la izquierda, para corregir se puede poner estilos inline con lo siguiente: ``` text-align:-webkit-center; ``` o  tambbien añadir a la tabla que este dentro del tag center, ``` display: inline-block; ``` .

* En las imagenes es mejor mantenerlas los mas ligeras posibles, debajo de los 100kb es ideal y debajo de los 255kb es lo standard