# La regla de oro en el desarrollo de emails es: si existe un atributo de HTML, úsalo en vez de CSS.

## Índice 
* [Metas](#Metas) 
* [Estilos](#Estilos) 
* [Body y Container Main](#Container Table) 
* [Tablas](#<table></table>)
* [Td](#<td></td>)
* [Imagenes](#Imagenes)
* [Tipografía](#Tipografia) 
* [Varios](#Varios) 
* [Clientes de servicio de mail](#Servicios de Mail)
* [Referencias](#Referencias)

* * *
## Contenido 

#### Metas

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

#### Estilos

* Usar estilos inline en cada elemento y/o los estilos en el head (algunos clientes de mail reconocen al style en el head y otros no, asi que los estilos inline nos ayudan en esos casos). 

* Formato de nombre de clases: nombre que tengan referencia al elemento; si se usa guiones usar uno porque yahoo no es compatible a clases con guion doble.

* Utilizar atributos HTML al máximo en lugar de CSS.


#### Container Table

* Añadir padding y margin de 0px en el body para evitar espacios inesperados de los browsers.

* Se puede usar un tag center (tener cuidado en Yahoo ya que le da una clase por default que podría cambiar el diseño del mail).

* Usar ``` <table></table> ```  que actua como el 'body' real del la estructura, con un ancho de 100%, ```border="0" ``` , ``` cellpadding = "0" ``` y ``` cellspacing = "0" ``` para quitar espacios entre las tablas.

* Los elementos tr y td funciones como fila y columna; si se crea una división más, se anida una nueva tabla: table>tr>td.

#### <table></table> 

* Con los atributos anteriores crear una tabla que tiene ancho de 600px y align center, este ancho es seguro para que el mail se muestre en casi todos los servcios de mail.

* En las siguientes tablas el ancho se puede manejar en porcentajes, asi se adapatará al momento de hacer un email adaptable; al cambiar el ancho de elemento padre, el resto de tablas se adaptará.

* Cuando hay elementos de tamaños específicos dentro de una tabla (como imagenes), es mejor poner tamaños exactos (px).

#### <td></td> 

* Para centrar el contenido usar el atributo ``` align="center" ``` .

* Para alinear verticalmente el contenido de una celda, usar ``` valing="top" ```. Este es un atributo HTML equivalente a verical-align en CSS.
 
* Es seguro utilizar relleno en los tables cell, los tags como div o p se comportan de manera diferente e inesperada, ademas que Outlook no los reconoce en estos elementos.

* Especificar cada uno de los valores del relleno: 
	1. ``` padding: 10px 3px 10px 4px; ``` 
	2. ``` padding-top:10px; padding-right:10px; padding-bottom:8px ; padding-left:5px; ``` .

* Si hay problemas con el padding (que la plataforma de envio de mail excluya los estilos CSS) crear espacios con celdas vacias: 
  ``` <tr><td style="font-size: 0; line-height: 0;" height="10">&nbsp;</td></tr> ``` , (el atributo height varia). 

* Se puede incluir estilos inline para el texto (font-family, font-size, color, text-decoration, etc) dentro de las celdas (td) para evitar que algunos clientes de mail sobre escriban tus estilos.


#### Imagenes

* Normalmente Outlook, Gmail y Yahoo bloquean las imagenes por default, es importante colocar un Alt correcto, para dar referencia al usuario del contenido de la imagen.

* Añadir a las imagenes ``` display: block; ``` para evitar que algunos clientes de mail añadan espacios debajo de las imagenes.

* Mantener el tamaño lo mas ligero posible, el tamaño standard es debajo de 250kb (100kb es el tamaño ideal).

* Si usas imagenes como enlaces con el atributo ``` border="0" ``` quitas el típico borde azul de los enlaces.

* Para clientes como Outlook establecer anchos definidos (como atributo Html), para clientes más amigables usar CSS clásico. 


#### Tipografias

* Fuentes como Arial, Verdana, Georgia, Times New Roman, Courier y Comic Sans son confiables y soportadas por la mayoria de los servicios de mail. 
 [Fonts en Email](https://help.sharpspring.com/hc/en-us/articles/115001033467-Using-Fonts-to-Get-the-Most-Out-of-Your-Email-Marketing)

* Apple Mail y algunos otros soportan @import y @font-face.

* Usar condicionales para versiones de Outlook, si es necesario.


#### Varios

* En Media Queries usar !important para poder reemplazar a los estilos inline del Html.

* Para los colores usar los seis carácteres del código hexagesimal. ex: #fffffff.

* En los tags table y td se puede usar el atributo bgcolor (color de fondo).

* El atributo backgorund="url" permite poner un fondo de imagen cuando en CSS no funciona, es amigable con algunos clientes mail.

* En caso de las etiquetas de enlace, se puede cambiar de color con estilos inline o con la etiqueta font:
  ``` <a href="#" style="color: #ffffff;"><font color="ffffff">link</font></a> ``` . 

* Border redondeados:
	1. Aplicar border-radius en el table cell (td) que envuelve el enlace.

* Relleno en un boton:
	1. Aumnetar el relleno en el table cell que envuelve al enlace.
	2. Aumentarlo en el mismo enlace, cambiando a display: inline-block.

* Asegurarse de que el href no este vacio, que contenga http:// o https:// , para no tener errores en las pruebas de envio.


## Servicios de Mail

* La mayoría de los clientes de correo web como Gmail, Outlook.com y Yahoo! Mail no permiten valores de los márgenes negativos. 

* Evita el uso de selectores por atributos, Gmail no es compatible con este tipo de selectores y ya no son necesarios para Yahoo Mail.


#### Outlook

* Para evitar que Outlook añada espacio entre las tablas usar ``` mso-table-lspace: 0pt !important; mso-table-rspace: 0pt !impotant; ``` .

* Para versiones modernas de Outlook añadir en las tablas ``` border-collapse: collapse ``` para evitar espacios entre ellas y sus bordes.

* Para Apple Mail, Outlook para Mac, Android Mail y iOS Mail usar webkit.

* ``` mso-line-height-rule: exactly; ``` fuerza a Outlook a respetar el alto de línea de la tabla.

* Outlook puede soportar fondo de imagen declaradas en el HTML, ignorando a las de CSS.

* Condicionales que permiten añadir fragmentos de HTML que sólo son leídos por las versiones indicadas de Outlook. 
 [Condicionales para Outlook](http://labs.actionrocket.co/microsoft-outlook-conditional-statements)

	``` <!--[if mso]>Outlook<![endif]--> ```


#### Yahoo

* Cuando un elemento tiene estilos muy especificos usar estilos inline para que Yahoo pueda reconocerlos.

* Con ``` style ="table-layout: fixed;" ``` se puede centrar contenido en una tabla.

* Yahoo mail añade estilos a las etiquetas ``` center ```, que aveces no centrar a los elementos y para corregir usar ``` text-align: -webkit-center; ``` .


#### Gmail 

* Gmail ahora soporta estilos en el ``` <head> ``` . 

* Soporta hasta cierta cantidad de carácteres por bloque de estilos, al superar ese número Gmail elimina ese bloque. 

* Los estilos importantes para el mail y amigables para Gmail, siempre deben ir primero. 

* Matener los media queries ``` @media ``` en bloques separados de los estilos principales. 

 [Actualizaciones en Gmail](https://emails.hteumeuleu.com/troubleshooting-gmails-responsive-design-support-ad124178bf81#.uc62hp58s)

####Móvil 

* Para evitar el crecimiento de tamaño del texto en los dispositivos móviles, se usa ``` text-size-adjust: 100% ``` con los prefijos que creas necesarios, para desactivar el comportamiento automático.

* Para las versiones movil de algunos servicios es mejor dejar los estilos inline de cada elemento.


* * *

## Referencias 

* [Building Email HTML](https://www.smashingmagazine.com/2017/01/introduction-building-sending-html-email-for-web-developers/)

* [Emails in Outlook](https://www.emailonacid.com/blog/article/email-development/tips_and_tricks_outlook.com)

* [Media Queries: max-width y min-width](https://www.emailonacid.com/blog/article/email-development/emailology_media_queries_demystified_min-width_and_max-width)

* [Email Development in Gmail](https://www.emailonacid.com/blog/article/email-development/12_things_you_must_know_when_developing_for_gmail_and_gmail_mobile_apps)
* [Gmail CSS Supported](https://developers.google.com/gmail/design/reference/supported_css)

* [Tipografias](https://envato.com/blog/experimental-typography-email/)

## Info adicional

* [HTeuMeuLeu en Medium](https://emails.hteumeuleu.com/)
* [Blog de Lee Munroe](http://www.leemunroe.com/blog/)
* [Email Meta Tag](https://www.emailonacid.com/blog/article/email-development/demystifying-meta-tags-in-email)
* [Background con VML](https://backgrounds.cm/)