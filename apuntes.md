# DNS
## Resolución
DNS es un servidor cuya función consiste en traducir IPs a nombres de dominio legibles y entendibles por el humano. Por ejemplo: 8.8.8.8 se traduce en www.google.com.

## Nombre de dominio
Se trata de un nombre fácil de recordar asociado a una dirección IP física de Internet.

## Niveles de dominio
Un nombre de dominio está dividido en varios niveles de dominio:

##### - Primer nivel o Top Level Domain
Se encuentra a la derecha del todo (.es / .com / .org ...).
##### - Segundo nivel o dominio
Es el TLD sumado al nombre que le precede (lfp.es / google.com).
##### - Tercer nivel o subdominio
Se compone de las 3 partes del nombre de dominio (www.google.com).

Aunque no es lo normal, existen más niveles de dominio (www.kali.edu.org).

## Zonas de búsqueda
Son dos: directa e inversa.
Las zonas de búsqueda directa facilitan la traducción de nombres de dominio a direcciones IP, lo que permite a los usuarios acceder a recursos en Internet.
Las zonas de búsqueda inversa asignan direcciones IP a nombres de dominio para tareas como diagnóstico de red y verificación de seguridad.

## Tipos de servidores
En cuanto al modo de funcionamiento de un servicio DNS, podemos clasificarlos en los siguientes tipos:1:

Servidor primario (maestro): en él se llevan a cabo todas las modificaciones sobre una o varias zonas. Almacena la copia original de la BD de la zona y se le denomina autorizado.

Servidor secundario (esclavo): contiene una copia de solo lectura de los archivos de zona que obtiene del servidor maestro (transferencia de zona), también es autorizado.

Servidor esclavo DNS
Servidor caché: No contiene información acerca de la zona y se utiliza para acelerar las consultas, almacenando las últimas realizadas.

Servidor cache DNS
Servidor reenviador (forwarder): Cuando un servidor DNS no tiene la respuesta a una consulta, puede acudir a este tipo de servidores que se utilizan para reducir el tráfico y las consultas DNS, ya que resuelven completamente la consulta y se comparte su caché.

Servidor solo autorizado: Se trata de servidores que están autorizado en una o varias zonas, como primario o secundario, pero no preguntan a otros servidores para resolver la petición.

Servidores raíz (root servers): En Internet existen un conjunto de servidores DNS autorizados para el dominio raíz «.», conocidos como servidores raíz (root servers). Contienen el fichero de la zona «.» que contiene información sobre los servidores DNS autorizados para cada uno de los dominios TLD.

## Funcionamiento

#### Consulta recursiva
resolución RECURSIVA: El servidor local se encargará de dar una respuesta COMPLETA al cliente y consultará a los servidores DNS intermedios que necesite en su nombre.

#### Consulta iterativa
resolución ITERATIVA: El servidor DNS local devuelve la mejor respuesta que puede ofrecer al cliente. Si no dispone de la información solicitada, indicará la IP del siguiente servidor de nombres autorizado
