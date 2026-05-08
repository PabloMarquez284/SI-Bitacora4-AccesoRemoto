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

Después de todas las comprobaciones, he generado dos llaves con el comando “**ssh-keygen \-t ed25519 \-C "pablomarquez.25@campuscamara.es"**”  
<img width="621" height="378" alt="image" src="https://github.com/user-attachments/assets/88cdc305-b52b-4dca-be00-66f66dde921a" />

Para hacer la transferencia de mi llave pública al servidor, he utilizado el comando “***ssh-copy-id \-p 2222 pabloml@localhost***” para copiarla.
<img width="840" height="277" alt="image" src="https://github.com/user-attachments/assets/76d781db-9f89-4676-b55b-10a375edc955" />

