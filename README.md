# Verificador servidor DHCP
<p>Este programa verifica el archivo /etc/dhcp.conf de un serivodor remoto, y a partir de una base de datos de direcciones MAC y otra de direcciones IP, revisa que no haya redes o equipos reciclados.</p>
<p>Instalacion:</p>
<ul>
	<li>1. Descargar el codigo fuente a la computadora con <code>git clone https://github.com/sebvif/dhcpverify.git</code>.</li>
	<li>2. Ir al directorio recien creado con <code>cd dhcpverify</code>.</li>
	<li>3. Generar un virtualenv con <code>virtualenv venv</code> y activarlo con <code>source venv/bin/activate</code>.</li>
	<li>4. Instalar las librerias requeridas con <code>pip install -r requirements.txt</code>.</li>
</ul>
<p>Utilizacion:</p>
<ul>
	<li>1. Asegurar que este activo el virtualenv y ubicarse en el directorio <code>~/dhcpverify/</code>.</li>
	<li>2. Con la base de datos de la semana en la carpeta mencionada ejecutar el programa <code>python dhcp_verify.py</code>.</li>
	<li>3. Cuando se solicite, ingresar el nombre del archivo y la hoja en que se encuentra la informacion.</li>
	<li>4. Seguir las instrucciones en pantalla. Es importante mencionar que se deberan comentar las lineas indicadas en el archivo de reciente creacion en el servidor remoto <code>~/tmp/dhcp.conf.new</code>. Al finalizar las correcciones se puede proceder a la copia del archivo con <code>sudo cp ~/tmp/dhcp.conf.new /etc/dhcp/dhcpd.conf</code>, para despues reiniciar el servicio <code>sudo systemctl restart isc-dhcp-server</code>.</li>
</ul>
<p>Recordar que el servicio genieacs debe estar corriendo para que la aplicacion funcione correctamente.</p>