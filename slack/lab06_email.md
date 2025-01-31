# Laboratorio 6: email en Linux

### Act. 6.1: enviar email usando $mail

#### Grabación de la actividad
[![asciicast](https://asciinema.org/a/h54VW7eXjRScEDFUcQnfASErS.svg)](https://asciinema.org/a/h54VW7eXjRScEDFUcQnfASErS)

#### Explicación del comando:
#### echo "Welcome to Network Computer Systems" | mail -s "Hello world" bob@anglia.bryant  -c  smith@anglia.bryant  -b  root@anglia.bryant

        echo "Welcome to Network Computer Systems"

La primera parte del comando imprime el mensaje "Welcome to Network Computer Systems".

Mediante la tubería ( | ) se pasa la salida de echo como entrada al comando $mail.

        mail -s "Hello world" bob@anglia.bryant -c smith@anglia.bryant -b root@anglia.bryant

Envía un correo electrónico con el asunto "Hello world" al destinatario (bob@anglia.bryant).

Además, se añade a Smith y a Root como destinatarios adicionales del mensaje, con la diferencia de que todos los destinatarios del correo pueden ver que Smith
también ha recibido el email (opción -c). Sin embargo, ningún otro destinatario sabrá que Root lo ha hecho (opción -b).

### Act. 6.2: revisando el email

#### Grabación de la actividad
[![asciicast](https://asciinema.org/a/kTvZfGSJiSw3tUyNdv1NWNxmT.svg)](https://asciinema.org/a/kTvZfGSJiSw3tUyNdv1NWNxmT)

### Act. 6.3: explorando $mail

#### Grabación de la actividad
[![asciicast](https://asciinema.org/a/hlQRfTILJm5mwSrdqhVRKtixQ.svg)](https://asciinema.org/a/hlQRfTILJm5mwSrdqhVRKtixQ)

#### ¿Qué contiene /var/spool/mail?
Este directorio contiene los emails que recibe un usuario en formato de texto plano.

#### ¿Cuáles son los puertos usados por SMTP y POP3?
- SMTP usa el puerto 25 por defecto.
- POP3 usa el puerto 110.
