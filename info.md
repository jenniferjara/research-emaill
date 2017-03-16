# La regla de oro en el desarrollo de emails es: si existe un atributo de HTML, úsalo en vez de CSS.

## Índice 
* [Metas](#Metas) 
* [Estilos](#Estilos) 
* [Contenido](#contenido) 
* [Varios](#varios) 
* [Clientes de servicio de mail](#servicios-de-mail)
* [Referencias](#Referencias)

* * *

### Metas

* Código para el navegador a fin que valide el código HTML de archivo: 
``` html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional //EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
```
* Soporte para los caracteres Unicode del documento:
``` html 
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" /> 
```
* Control en las vistas móvil 
``` html 
<meta name="viewport" content="width=device-width"> 
```
* Permite una vista responsive en Windows Phone: 
``` html 
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
``` 
* Evita que los números telefonicos aparezcan como link
``` html
<meta name="format-detection" content="telephone=no">
``` 
* Deshabilita el auto-scale en iOS 10 mail: 
``` html 
<meta name="x-apple-disable-message-reformatting"> 
```

### Estilos

* En el selector universal añadir text-size-adjust: 100% para evitar el crecimiento del texto en versiones moviles, con los prefijo por navegador.
* En el Body usar padding y margin 0.
* Si usas titulos (h1,h2,...) párrafos o divs añadir padding y margin 0.
* Border-collapse: collapse; en las tablas para evitar espacios en el border.
* Display block; en las imagenes (img) para evitar que se añada espacios debajo de ellas.
* Usar los seis caracteres del código hexadecimal de los colores.

* * *

### Contenido

A. Tablas

* En las tablas agregar atributos border=0, cellpadding=0, cellspacing=0.
* Una tabla con una ancho de 100% que actuará como en body del documento. 
* Una tabla con un ancho de 600px, es un ancho seguro para la visualizacipon del documento en los clientes de mail y align center para centrar las celdas.
* En las siguientes tablas usar width de 100% para que ocupe todo el ancho de la tabla de 600px.

B. Celdas

* En las celdas (td) agregar atributos align(alineamiento) y valign(alineamiento vertical).
* Es seguro usar relleno en las celdas (td), en otros elementos (como divs o párrafos) se comportan de manera inesperada en Outlook. 
* Los estilos para fuentes y textos son seguros de aplicar en las celdas.

C. Fondos

* Añadir color de fondo con el atributo bgcolor y con los seis caracteres hexadecimales.
* Añadir una imagen de fondo con el atributo background en las celdas (td).

D. Botones

1. Con Borde
 + Una tabla sin ancho. (tr>td>)
 + Usar una tabla con border-collapse separate, border-radius y borde. (tr>)
 + Una celda con padding y estilos de fuentes.
 + Un enlace con sus estilos especificos.

2. Con Relleno
 + Una tabla sin ancho. (tr>)
 + Una celda con padding, border-radius y color de fondo.
 + Un enlace con sus estilos especificos.

* Colocar en los enlaces href validos para las pruebas del mail.

* * *

### Varios

A. Imagenes

* Usar Alt adecuados para dar referencia al usuario del contenido de la imagen en caso no carguen.
* Mantener con un tamaño ligero en las imágenes (standard 250kb - ideal 100kb).
* Si la imagen se usa como enlace, con borde 0 se evita el borde azul típico de los enlaces.
* Para evitar que las imagenes tengan el border azul al usarlas de enlaces, aplicar el atributo border=0.
* Establecer ancho como atributo HTML para Outlook, y CSS para Gmail y Yahoo.
* Para Outlook establecer ancho con atributo HTML, y para Gmail y Yahoo usar CSS. 

B. Tipografias

* Fuentes como Arial, Comic Sans, Courier, Georgia, Verdana, Times New Roman; son confiables y soportadas por la mayoria de los servicios de mail. 
 [Fonts en Email](https://help.sharpspring.com/hc/en-us/articles/115001033467-Using-Fonts-to-Get-the-Most-Out-of-Your-Email-Marketing)
* El método @import tiene soporte en dispositivos iOS y Apple Mail. No tiene soporte en Gmail y Outlook o Yahoo.

C. Videos 

* El video es compatible con iOS, Apple Mail y Outlook.com, usar media queries para ocultar o mostrar segun el tipo de cliente.

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

## Referencias

* [CSS Support Guide](https://www.campaignmonitor.com/css/) 
* [Building Email HTML](https://www.smashingmagazine.com/2017/01/introduction-building-sending-html-email-for-web-developers/)
* [Media Queries: max-width y min-width](https://www.emailonacid.com/blog/article/email-development/emailology_media_queries_demystified_min-width_and_max-width)
* [Emails in Outlook](https://www.emailonacid.com/blog/article/email-development/tips_and_tricks_outlook.com)
* [Email Development in Gmail](https://www.emailonacid.com/blog/article/email-development/12_things_you_must_know_when_developing_for_gmail_and_gmail_mobile_apps)
* [Gmail CSS Supported](https://developers.google.com/gmail/design/reference/supported_css)
* [Tipografias](https://envato.com/blog/experimental-typography-email/)

### Más información

* [HTeuMeuLeu en Medium](https://emails.hteumeuleu.com/)
* [Blog de Lee Munroe](http://www.leemunroe.com/blog/)
* [Email Meta Tag](https://www.emailonacid.com/blog/article/email-development/demystifying-meta-tags-in-email)
* [Background con VML](https://backgrounds.cm/)