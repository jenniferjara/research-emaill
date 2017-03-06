1. Body y Main Table

	* Body: añadir padding y magin 0px para evitar espacios inesperados.
	* Table: que actua como el 'body' real del la estructura, añadir los siguientes atributos directamente en el html width de 100% , cellpd y cellsp en 0 para quitar espacios

La regla de oro en el desarrollo de emails en HTML es: si un atributo de HTML existe úsalo en vez de CSS.
Si se necesita añadir un color de fondo, en este tag es donde se debe colocar.

2. Contenido

	*Table: añadir los atributos anterioes y esta vez con un width de 600px y align center, es un ancho seguro para que el mail se muestre en casi todas las pantallas de pc.
	Tambien de añade estilos inline 'border-collapse: collapse' para evitar de versiones modernas de Outlook añadan espacios entre la tabla y el border.