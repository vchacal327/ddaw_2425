# Laboratorio 4: demonios y procesos

### Act. 4.1: explorando los procesos en ejecución

#### Grabación de la actividad
[![asciicast](https://asciinema.org/a/46MPgNJoHF1St4Aazb1DnmlOk.svg)](https://asciinema.org/a/46MPgNJoHF1St4Aazb1DnmlOk)

#### Descripción de los procesos

- ##### mariadbd (PID: 992)
El servidor de base de datos MariaDB está gestionando o consultando una base de datos.

- ##### /sbin/init (PID: 1)
El trabajo de este proceso es inicializar el sistema, configurar los servicios y gestionar el proceso de arranque.

- ##### python3 /usr/bin/asciinema rec lab41 (PID: 1243)
Este proceso está grabando una sesión de terminal utilizando la herramienta Asciinema.

- ##### dockerd (PID: 663)
El demonio Docker se está ejecutando, gestionando contenedores.

- ##### kworker/u2:0-ext4-rsv-conversion (PID: 9)
- ##### kworker/0:4-events (PID: 138)
 Se trata de un proceso del kernel que se encarga de tareas relacionadas con el sistema de archivos ext4, principalmente redimensionar o reservar espacio.

- ##### apache2 -DFOREGROUND (PID: 998)
El servidor HTTP Apache se está ejecutando en primer plano, probablemente sirviendo peticiones web.

- ##### containerd (PID: 454)
Un runtime de contenedores que se encarga de gestionar contenedores, trabajando en conjunnto con el proceso dockerd.

- ##### systemd-journald (PID: 212)
El servicio journald se encarga de registrar los eventos del sistema.

- ##### rcu_preempt (PID: 15)
Se trata de un hilo del kernel utilizado para operaciones de Lectura-Copia-Actualización.

### Act. 4.2: explorando procesos de red

#### Grabación de la actividad
[![asciicast](https://asciinema.org/a/JlI2AL4mlUFU6y1I3Mlyf6UGz.svg)](https://asciinema.org/a/JlI2AL4mlUFU6y1I3Mlyf6UGz)

#### Descripción de los procesos

- ##### 22/tcp (ssh)
Permite el inicio de sesión remoto seguro y cifrado, además de la ejecución de comandos en la máquina ajena.

- ##### 80/tcp (http)
Se trata de un proceso de servidor web HTTP. Se encarga de servir sitios o aplicaciones web a los usuarios a través de Internet o de una red local.

- ##### 8080/tcp (http-proxy)
Asociado al puerto 8080, que se utiliza a menudo para servicios web, servidores proxy o entornos de desarrollo de aplicaciones.

### Act. 4.3: explorando las señales UNIX

#### Grabación de la actividad
[![asciicast](https://asciinema.org/a/KZsLNgu67ZEP4ILKqS6e9IUke.svg)](https://asciinema.org/a/KZsLNgu67ZEP4ILKqS6e9IUke)

#### Explicación del comando $kill -l
El comando kill -l lista todas las señales disponibles que se pueden enviar a los procesos. Cada señal tiene un número y un nombre, y se utilizan para comunicarse con los procesos, por ejemplo, para terminarlos, pausarlos o señalar acciones específicas:

| **Número de Señal** | **Nombre de Señal** | **Descripción**                                 |
|----------------------|---------------------|-------------------------------------------------------|
| 1                    | SIGHUP              | Cuelgue detectado en la terminal de control o muerte del proceso de control |
| 2                    | SIGINT              | Interrupción procedente del teclado (por ejemplo, `Ctrl+C`)|
| 3                    | SIGQUIT             | Finalización procedente del teclado  |
| 4                    | SIGILL              | Instrucción ilegal                         |
| 5                    | SIGTRAP             | Trampa de traza/punto de interrupción (usada por depuradores) |
| 6                    | SIGABRT             | Señal de aborto del proceso |
| 7                    | SIGBUS              | Acceso a una dirección de memoria no válida          |
| 8                    | SIGFPE              | Excepción de coma flotante |
| 9                    | SIGKILL             | Terminación forzosa del proceso, no puede ser interceptada o ignorada |
| 10                   | SIGUSR1             | Señal definida por el usuario 1                      |
| 11                   | SIGSEGV             | Referencia inválida a memoria   |
| 15                   | SIGTERM             | Señal de terminación, puede ser interceptada o ignorada |
| 19                   | SIGSTOP             | Detiene el proceso, no se puede interceptar ni ignorar |
| 20                   | SIGTSTP             | Señal de pausa en el terminal (por ejemplo, `Ctrl+Z`) |

### Act. 4.4: procesos y redes

#### Grabación de la actividad
[![asciicast](https://asciinema.org/a/6WA0l20RVSQ1HF0XszmPJc9re.svg)](https://asciinema.org/a/6WA0l20RVSQ1HF0XszmPJc9re)

#### ¿Qué es sftp y ssh?
- SFTP (Secure File Transfer Protocol) es un método seguro de transferencia de archivos entre sistemas a través de una conexión SSH cifrada. Mantiene la seguridad al cifrar tanto las credenciales de autenticación como los datos.

- SSH (Secure Shell) es un protocolo de red criptográfico que proporciona acceso remoto seguro y ejecución de comandos a través de una conexión cifrada. Se utiliza ampliamente para gestionar servidores de forma segura.

#### ¿Por qué se desaconseja el uso de telnet en el "mundo real"?
Telnet transmite datos, incluidas las credenciales de inicio de sesión, en texto plano, lo que lo hace muy vulnerable a las escuchas y a los ataques de intermediario. Se recomiendan alternativas seguras como SSH porque cifran la comunicación y garantizan un acceso seguro.