#La regla de oro en el desarrollo de emails es: si existe un atributo de HTML, úsalo en vez de CSS.

## Índice 
* [Metas](#Metas) 
* [Style](#Style) 
* [Body y Table Main](#Body y Main Table) 
* [Tablas](#<table></table>)
* [Td](#<td></td>)
* [Imagenes](#Imagenes)
* [Tipografía](#Tipografia) 
* [Varios](#Varios) 
* [Clientes de servicio de mail](#Según tipos de clientes de mail)
* [Referencias](#Referencias)

* * *

####Metas

* Código para el navegador a fin que valide el código HTML de archivo: 
``` html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional //EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
```

* Brinda soporte para los caracteres Unicode del documento:
``` html 
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" /> 
```

* Control en las vistas móvil (aunque no estamos seguros que funcione del todo bien, pero...) 
``` html 
<meta name="viewport" content="width=device-width"> 
```

* Permite una vista responsive en Windows Phone: 
``` html 
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
``` 

* Evita que los números telefonicos aparezcan como link (cambiar a ``` telephone=yes ``` para que se vean como links)
``` html
<meta name="format-detection" content="telephone=no">
``` 

* Deshabilita el auto-scale en iOS 10 mail: 
``` html 
<meta name="x-apple-disable-message-reformatting"> 
```

####Style

* Usar estilos inline en cada elemento y/o los estilos en el head (algunos clientes de mail reconocen al style en el head y otros no, asi que los estilos inline nos ayudan en esos casos). 

* Formato de nombre de clases: nombre que tengan referencia al elemento; si se usa guiones usar uno porque yahoo no es compatible a clases con guion doble.


####Body y Main Table

* Usar al máximo los atributos Html.

* Añadir padding y margin de 0px en el body para evitar espacios inesperados de los browsers.

* Se puede usar un tag center (tener cuidado en Yahoo ya que le da una clase por default).

* Usar ``` <table></table> ```  que actua como el 'body' real del la estructura, con un ancho de 100% y ``` cellpadding = "0" ``` y ``` cellspacing = "0" ``` para quitar espacios entre las tablas.

* Los elementos tr y td funciones como fila y columna; si se crea una división más, se anida una nueva tabla: table>tr>td.

####<table></table> 

* Añadir los atributos anteriores ( ``` cellpadding = "0" ``` y ``` cellspacing = "0" ``` ) esta vez con un ancho de 600px y align center, el ancho de 600px es seguro para que el mail se muestre en casi todos los servcios de mail.

* En las siguientes tablas el ancho se puede manejar en porcentajes, asi se adapatará al momento de hacer el email responsive; al cambiar el ancho de elemento padre, el resto de tablas se adaptará.

* Cuando hay elementos de tamaños específicos dentro de una tabla (como imagenes), es mejor poner tamaños exactos (px).

####<td></td> 

* Para centrar el contenido usar el atributo ``` align="center" ``` .

* Para alinear verticalmente el contenido de la celda hacia arriba, usar ``` valing="top" ```. Este es un atributo HTML equivalente a verical-align en CSS.
 
* Es seguro utilizar padding en los tag td, los tags como div o p se comportan de manera diferente e inesperada, ademas que Outlook no lo reconoce en estos elementos.

* Especificar cada uno de sus valores: ``` padding: 10px 3px 10px 4px; ``` o ``` padding-top:10px; padding-right:10px; padding-bottom:8px ; padding-left:5px; ``` .

* Si hay problemas con el padding (que la plataforma de envio de mail excluya los estilos CSS) crear espacios con celdas vacias: 
  ``` <tr><td style="font-size: 0; line-height: 0;" height="10">&nbsp;</td></tr> ``` , (el atributo height varia). 

* Incluir dentro de ``` <td></td> ``` estilos de texto (font-family, font-size, color, text-decoration, etc) para evitar que algunos clientes de mail subcriban los estilos de fuentes.


####Imagenes

* Normalmente Outlook, Gmail y Yahoo bloquean las imagenes por default, es importante colocar un Alt correcto, para dar referencia al usuario del contenido de la imagen.

* Añadir a las imagenes ``` display: block; ``` para evitar que algunos clientes de mail añadan espacios debajo de las imagenes.

* Mantener el tamaño lo mas ligero posible, el tamaño standard es debajo de 250kb (100kb es el tamaño ideal).

* Si usas imagenes como enlaces con el atributo ``` border="0" ``` quitas el típico borde azul de los enlaces.

* Para clientes como Outlook establecer anchos definidos (como atributo Html), para clientes más amigables usar CSS clásico. 


####Tipografias

* Fuentes como Arial, Verdana, Georgia, Times New Roman, Courier, etc son confiables y soportadas por la mayoria de los servicios de mail. [Más info](https://help.sharpspring.com/hc/en-us/articles/115001033467-Using-Fonts-to-Get-the-Most-Out-of-Your-Email-Marketing "")

* Apple Mail y algunos otros soportan @import y @font-face.

* Usar condicionales para versiones de Outlook, si es necesario.


####Varios

* En Media Queries usar !important para poder reemplazar a los estilos inline del Html.

* Para los colores usar los seis carácteres del código hexagesimal. ex: #fffffff.

* En los tags table y td se puede usar el atributo bgcolor (color de fondo).

* El atributo backgorund="url" permite poner un fondo de imagen, cuando con CSS no funciona, es amigable con algunos clientes mail.

* En caso de las etiquetas de enlace, se puede cambiar de color con estilos inline o con la etiqueta font:
  ``` <a href="#" style="color: #ffffff;"><font color="ffffff">link</font></a> ``` . 

* Para crear botones con bordes redondeados, aplicar border-radius en la etiqueta td que envuelve el enlace: ``` <a href="#"></a> ``` .

* Para aumentar el padding de un boton hay dos maneras: aumentarlo en el td que contiene al link o en el mismo link cambiando el display a inline-block.

* Colocar un href válido en los enlaces (para no tener errores en las pruebas de envio).


##Según tipos de clientes de mail

* La mayoría de los clientes de correo web como Gmail, Outlook.com y Yahoo! Mail no permiten valores de los márgenes negativos. 

* Evita el uso de selectores por atributos, Gmail no es compatible con este tipo de selectores y Yahoo ya acepta los selectores por clases y Id.


####Outlook

* Para evitar que Outlook añada espacio entre las tablas usar ``` mso-table-lspace: 0pt !important; mso-table-rspace: 0pt !impotant; ``` .

* Añadir a las tablas estilos inline ``` border-collapse: collapse ``` para evitar que versiones modernas de Outlook añadan espacios entre la tabla y el border de la tabla.

* Para Apple Mail, Outlook para Mac, Android Mail y iOS Mail usar webkit.

* ``` mso-line-height-rule: exactly; ``` fuerza a Outlook a respetar el alto de línea de la tabla.

* Condicionales que permiten añadir fragmentos de HTML que sólo son leídos por las versiones indicadas de Outlook. [Más info](http://labs.actionrocket.co/microsoft-outlook-conditional-statements "Más info") 

	``` <!--[if mso]>Outlook<![endif]--> ```


####Yahoo

* Yahoo mail añade a las etiquetas ``` center ``` una clase por default, que tiene un ``` text-align: center, ``` y que hace que los elementos se alinien a la izquierda; para corregir usar estilos inline con lo siguiente: ``` text-align:-webkit-center; ``` o  tambien añadir a la tabla que este dentro del tag center, ``` display: inline-block; ``` .

* Con ``` Margin: 0 auto; ``` se puede centrar una tabla en Yahoo y Chrome. 

####Gmail 

* Gmail ahora soporta estilos en el ``` <head> ``` . 

* Soporta hasta cierta cantidad de carácteres por bloque de estilos, al superar ese número Gmail elimina ese bloque. 

* Los estilos importantes para la plantilla y amigables para Gmail, siempre deben ir primero. 

* Matener los media queries ``` @media ``` en bloques separados de los estilos principales. 


####Móvil 

* Para evitar el crecimiento de tamaño del texto en los dispositivos móviles, se usa ``` text-size-adjust: 100% ``` con los prefijos que creas necesarios. 

* Para las versiones movil de algunos servicios es mejor dejar los estilos inline de cada elemento.

* * *

###Referencias 

* [HTeuMeuLeu en Medium](https://emails.hteumeuleu.com/ "HTeuMeuLeu")
* [HTML email in Gmail ](https://www.emailonacid.com/blog/article/email-development/12_things_you_must_know_when_developing_for_gmail_and_gmail_mobile_apps "")
* [Actualizaciones en Gmail](https://emails.hteumeuleu.com/troubleshooting-gmails-responsive-design-support-ad124178bf81#.uc62hp58s "")
* [Gmail CSS Supported](https://developers.google.com/gmail/design/reference/supported_css "")
* [VML Background](https://backgrounds.cm/ "")
* [Imagenes de fondo con VML](https://backgrounds.cm/ "")
* [Tipografias](https://envato.com/blog/experimental-typography-email/ "")

###Info adicional

* [Blog de Lee Munroe](http://www.leemunroe.com/blog/ "")
* [Email Meta Tag](https://www.emailonacid.com/blog/article/email-development/demystifying-meta-tags-in-email "")
