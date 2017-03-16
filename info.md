# La regla de oro en el desarrollo de emails es: si existe un atributo de HTML, úsalo en vez de CSS.

## Índice 
* [Metas](#Metas) 
* [Estilos](#Estilos) 
* [Contenido](#contenido) 
* [Varios](#Varios) 
* [Clientes de servicio de mail](#servicios-de-mail)
* [Referencias](#Referencias)

* * *

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

* Para evitar el crecimiento del texto en versiones moviles usar text-size-adjust: 100%; .
* Usar padding y margin 0 en el body.
* Border-collapse: collapse; en las tablas para evitar espacios en el border.
* display block; en las imagenes para evitar que se añada espacios debajo de ellas.
* Colores: usar los seis caracteres del código hexagesimal.

* * *

#### Contenido

A. Tablas

* Usar atributos html al máximo.
* En tablas agregar atributos border=0, cellpadding=0, cellspacing=0.
* Una tabla con una ancho de 100% que actuará como en body del documento. 
* Una tabla con un ancho de 600px, es un ancho seguro para la visualizacipon del documento en los clientes de mail y align center para centrar las celdas.
* En las siguientes tablas usar width de 100% para que ocupe todo el ancho de la tabla de 600px.

B. Celdas
* En las celdas (td) agregar atributos align(alineamiento) y valign(alineamiento vertical).
* Es seguro usar estilos de relleno en las celdas(td), en otros elementos (como divs o párrafos) se comportan de manera inesperada en Outlook.  
* Estlos de fuentes y textos son seguros de aplicar en las celdas.

C. Fondos
* Añadir color de fondo con bgcolor (atributo HTML) y los colores en codigo hexagesimal.
* Para imagenes de fondo usar el atributo HTML background en las celdas (td)

D. Botones

* tabla width 100%>tr>td>table sin width>tr>td>table bordercollapse separate, border y border radius>tr>td padding y estilos de fonts>a estilos espacificos para enlace

* tabla width 100%>tr>td>table sin width>tr>td border-radius, color de fondo>a estilos especificos del enlace.

* Colocar en los enlaces href validos para las pruebas del mail.

* * *

### Servicios de Mail

A. Outlook
* Evitar espaciado en tablas:  mso-table-lspace: 0pt !important; mso-table-rspace: 0pt !impotant; .
* Fuerza a Outlook a respetar el alto de la tabla: mso-line-height-rule: exactly; .
* Agregar condicionales <!--[if mso]>Outlook<![endif]--> para especificaciones de estilos, fondos de imagen o estructura en Outlook.
*  Margin (con mayúscula) funciona en Outlook.

B. Yahoo 
* Centrar los elementos en una tabla con table-layout: fixed; .
* Para estilos especificos en un elemnto usar estilos inline con !important.

C. Gmail
* Soporta estilos en el head y especificaciones en las media queries usando !important.
* Usar un bloque para estilos generales y otro para Media Queries.
* Gmail no es compatible con selectores de atributos y para Yahoo ya no es necesario el uso de ellos.
* 

* * *

#### Varios

A. Imagenes

* Usar Alt adecuados para dar referencia al usuario del contenido de la imagen en caso no carguen.
* Mantener un tamaño ligero en las imágenes (standard 250kb - ideal 100kb).
* Si la imagen se usa como enlace, con borde 0 se evita el borde azul típico de los enlaces.
* Establecer ancho como atributo HTML para Outlook, y CSS para Gmail y Yahoo.
* Para Outlook establecer ancho con atributo HTML, y para Gmail y Yahoo usar CSS. 


B. Tipografias

* Fuentes como Arial, Verdana, Georgia, Times New Roman, Courier y Comic Sans son confiables y soportadas por la mayoria de los servicios de mail. 
 [Fonts en Email](https://help.sharpspring.com/hc/en-us/articles/115001033467-Using-Fonts-to-Get-the-Most-Out-of-Your-Email-Marketing)

* Apple Mail y algunos otros soportan @import y @font-face.

C. Videos

* El video es compatible con iOS, Apple Mail y Outlook.com, usar media queries para ocultar o mostrar segun el tipo de cliente

* * * 

## Referencias 

* [Building Email HTML](https://www.smashingmagazine.com/2017/01/introduction-building-sending-html-email-for-web-developers/)

* [Emails in Outlook](https://www.emailonacid.com/blog/article/email-development/tips_and_tricks_outlook.com)

* [Media Queries: max-width y min-width](https://www.emailonacid.com/blog/article/email-development/emailology_media_queries_demystified_min-width_and_max-width)

* [Email Development in Gmail](https://www.emailonacid.com/blog/article/email-development/12_things_you_must_know_when_developing_for_gmail_and_gmail_mobile_apps)
* [Gmail CSS Supported](https://developers.google.com/gmail/design/reference/supported_css)

* [Tipografias](https://envato.com/blog/experimental-typography-email/)


* [HTeuMeuLeu en Medium](https://emails.hteumeuleu.com/)
* [Blog de Lee Munroe](http://www.leemunroe.com/blog/)
* [Email Meta Tag](https://www.emailonacid.com/blog/article/email-development/demystifying-meta-tags-in-email)
* [Background con VML](https://backgrounds.cm/)