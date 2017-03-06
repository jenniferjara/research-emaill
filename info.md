1. Body y Main Table

	* Body: añadir padding y magin 0px para evitar espacios inesperados.
	* Table: que actua como el 'body' real del la estructura, añadir los siguientes atributos directamente en el html width de 100% , cellpd y cellsp en 0 para quitar espacios


La regla de oro en el desarrollo de emails en HTML es: si un atributo de HTML existe úsalo en vez de CSS.
Si se necesita añadir un color de fondo, en este tag es donde se debe colocar.
En la tabla un tr es igual a una fila, y un td a una columna.

2. Contenido

	*Table: añadir los atributos anteriores y esta vez con un width de 600px y align center, es un ancho seguro para que el mail se muestre en casi todas las pantallas de pc.

En las tablas siguientes es de preferencia que el ancho ocupe todo el ancho la tabla principal entonces se usan los porcentajes, ya que asi se adapatará al momento de hacer el email responsive, si se desea cambiar el ancho solo se cambiará el ancho de elemento padre.

Tambien se añade estilos inline 'border-collapse: collapse' para evitar de versiones modernas de Outlook añadan espacios entre la tabla y el border.

En caso de los colores, es preferente utilizar los seis carácteres del código hexagesimal.

Cuando se utiliza padding en email, debe especificar cada uno de sus valores, de esta forma 'padding: 10px 3px 10px 4px;' o en su forma larga.
Tener en cuenta que es seguro usar padding en los tag td.
Como en las tablas el margin no funciona, se usa celdas vacias para crear estos margenes.

En caso de las etiquetas de enlace, se puede cambiar de color con estilos inline o con la etiqueta font, va dentro del tag a usando el atributo html 'color' 

```html 
<a href="#" style="color: #ffffff;"><font color="ffffff">link</font></a>
```