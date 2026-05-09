# BITÁCORA IV

## FASE 1: Despliegue de la estructura

Primero he creado una carpeta en el escritorio de nombre “SI\_Bitacora\_PabloMarquez” y dentro un archivo llamado “docker-compose.yml”: Dentro de ese archivo he hecho que se levanten dos servicios: un servidor SSH y un entorno gráfico (escritorio) vía RDP/Web, donde RDp significa Puerto estándar de Escritorio Remoto.

Al crear el archivo al completo, tuve un par de fallos:
1. El primero fue la manera de **indentar el código**, ya que en los archivos yml no se puede usar **tabulador**. Por ello, cambié el uso del tabulador por **dos espacios**.  
2. El segundo fue que al ejecutar el comando para la instalación de los servicios, no tenía abierto **docker**, y es por eso que el sistema no podía encontrar el archivo especificado. Una vez iniciado el docker, no tuve ningún problema más. En la imagen podemos ver el **error** que me salía:
<img width="1043" height="168" alt="image" src="https://github.com/user-attachments/assets/6d623acb-4edb-4692-9b3a-a955b551b146" />

En esta imagen podemos ver como, con el comando “**docker-compose up \-d**”, la instalación de los servidores y sus respectivos contenedores han sido creados e iniciados con éxito:![][image2]
<img width="1028" height="186" alt="image" src="https://github.com/user-attachments/assets/dbfcbbb6-5ab8-4be3-9543-c75f6b7c2587" />

Para verificarlo, con el comando “**docker ps**” podemos ver si se ha creado correctamente.  
<img width="886" height="207" alt="image" src="https://github.com/user-attachments/assets/018fd493-7a96-4787-bba0-9016a27696cf" />


## FASE 2: SSH: Forjando la Llave Maestra
Al ejecutar el comando “**ssh pabloml@localhost \-p 2222**”, me he conectado al contenedor SSH. En este caso, he creado yo mi propio usuario y contraseña.  
<img width="650" height="164" alt="image" src="https://github.com/user-attachments/assets/badc9d80-987f-4af4-8211-c1c4de246135" />

Para comprobar que el **servidor SSH** funcione de forma segura, con los comandos "**pwd**" y "**ls -l**" podemos ver los archivos y carpetas de condiguracion de dicho servidor. Concretamente, **sshd.pid** indica que SSH está activo y en ejecución.
<img width="566" height="196" alt="image" src="https://github.com/user-attachments/assets/a742ebb6-f0c4-47e7-baf7-54c317952d0d" />

Después de todas las comprobaciones, he generado dos llaves con el comando “**ssh-keygen \-t ed25519 \-C "pablomarquez.25@campuscamara.es"**”  
<img width="621" height="378" alt="image" src="https://github.com/user-attachments/assets/88cdc305-b52b-4dca-be00-66f66dde921a" />

Para hacer la transferencia de mi llave pública al servidor, he utilizado el comando “***ssh-copy-id \-p 2222 pabloml@localhost***” para copiarla.
<img width="840" height="277" alt="image" src="https://github.com/user-attachments/assets/44d5a446-7634-4406-bed9-c6742ee64477" />


## FASE 3: RDP: El Escritorio en tu Navegador
Ahora, es momento de abrir mi cliente de **Escritorio Remoto**, en este caso como estoy en windows, realizó la conexión por **MSTSC** pulsando Windows \+ R.
<img width="452" height="274" alt="image" src="https://github.com/user-attachments/assets/8c8c92dd-f31b-478a-abc4-190604dfbf03" />
<img width="536" height="296" alt="image" src="https://github.com/user-attachments/assets/58d1a840-18a1-42e8-83ee-130a74f4133d" />

Al intentar acceder a **localhost:3389**, me da error ya que mi equipo no se puede conectar al equipo remoto. 
<img width="693" height="205" alt="image" src="https://github.com/user-attachments/assets/2b1764e1-8b66-4170-b8f4-8e88de7cc143" />

Para solucionarlo, he ido a **http:/localhost:3000** para ver el escritorio de Ubuntu dentro de mi navegador. Esto es gracias a **Apache Guacamole**, ya que deja acceder a equipos y servidores remotos sin la necesidad de instalar un software cliente,  
<img width="1919" height="970" alt="image" src="https://github.com/user-attachments/assets/f7bc9eb2-449f-44a3-a101-32b4fbc45802" />

Para probar que va todo correctamente, he creado mediante la terminal un archivo en el escritorio llamado “**PRUEBA\_LOGRADA.txt**”, donde dentro pongo un mensaje para el docente, comentandole el logro de dicha actividad.  
<img width="941" height="74" alt="image" src="https://github.com/user-attachments/assets/6e63dd23-6957-487d-925e-fe6e4c3943d6" />
<img width="1919" height="710" alt="image" src="https://github.com/user-attachments/assets/9395de11-1554-47c4-af3e-ab087f44d242" />


## REFLEXIÓN FINAL
En conclusión, creo que **SSH** es más usado en servidores de producción que **RDP** porque es mucho más **ligero y seguro**. Este solo necesita comandos para funcionar, es decir, lo necesario para administrar un servidor, por lo que consume muy poca red. Además, lleva muchos años siendo el **estándar de Linux**.  
Sin embargo, **RDP** tiene que enviar toda la imagen del escritorio constantemente, lo que consume muchos más recursos y potencia del servidor. Por ello, está más pensado para usuarios que necesitan ver un **escritorio**, no para administrar servidores donde todo se hace con **comandos**. 


## REFERENCIAS
Me he guiado y ayudado con el documento que nos ha implementado el docente para realizar la actividad.
