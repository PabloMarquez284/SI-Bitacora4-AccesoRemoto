# MEMORIA TÉCNICA 

**Alumno**: Pablo Márquez López  
**Ciclo**: 1ºDAW  
**Fecha**: 15/05/26

## ÍNDICE 

[1.1 Introducción](#1-introduccion)

[1.2 ¿Qué problema de la empresa resolvemos con Guacamole y Docker?](#2-pregunta1)

[1.3 ¿Por qué elegimos esta solución y no conectar directamente por RDP a cada máquina?](#3-pregunta2)

[1.4 Conclusión](#4-conclusion)

[2. Estimación de Costes de Infraestructura](#4-estimacion)

## 1.1 Introducción 

Actualmente, la gestión de varios sistemas de forma eficiente es una necesidad fundamental en cualquier entorno. Para ello, vamos a ver qué problema podemos resolver con **Apache Guacamole** y **Docker**, dos herramientas que juntas permiten simplificar la administración remota de sistemas, reduciendo así costes y mejorando la seguridad.

## 1.2 ¿Qué problema de la empresa resolvemos con Guacamole y Docker? 

Para la solución a este problema, es importante tener en cuenta que gestionar múltiples servidores implica conectarse **individualmente** a cada máquina, con sus propias IPs y configuraciones. Esto era lento, desorganizado y difícil de mantener. Por esa razón, resolvemos esto con Apache Guacamole y Docker.

Con **Apache Guacamole** centralizamos todos los accesos remotos en una única interfaz web, accesible desde cualquier navegador sin instalar nada en el equipo del técnico. Esto aporta centralización, ahorro de recursos y mayor control de seguridad.

Y con **Docker** creamos contenedores, es decir,  entornos virtuales ligeros que funcionan dentro de un único servidor físico. Esto ahorra hardware, permite levantar o apagar entornos en segundos y facilita las copias de seguridad. 

## 1.3 ¿Por qué elegimos esta solución y no conectar directamente por RDP a cada máquina?

Conectar por RDP directamente a cada máquina **obliga** a tener el puerto **RDP abierto** en cada una, lo que aumenta los riesgos de seguridad. Además, el técnico necesita **instalar un cliente RDP**, conocer la **IP** de cada equipo y no existe ningún registro centralizado de accesos.

En cambio, con **Guacamole**, todas las conexiones pasan por un **único punto controlado**, lo que permite gestionar permisos, registrar quién accede y cuándo, y hacerlo todo desde un simple navegador web. Es una solución mucho más segura, ordenada y profesional.

## 1.4. Conclusión 

La combinación de **Docker** y **Guacamole** resuelve de forma eficiente los problemas de gestión remota en una empresa. Además, permite centralizar el acceso, reducir costes de hardware y mejorar la seguridad, evitando los riesgos que supone exponer múltiples conexiones RDP individuales. Por tanto, es una solución escalable y preparada para un entorno profesional.​​​​​​​​​​​​​​​​  


## 2. Estimación de Costes de Infraestructura
En la siguiente tabla podemos ver la estimación de costes de la infraestructura Cloud, con sus respectivos cálculos y datos necesarios.
<img width="539" height="196" alt="image" src="https://github.com/user-attachments/assets/384186df-7dbd-404f-9ecc-bc2685e803a9" />  
También he implementado la tabla con los costes en un pdf dentro del repositorio, dentro de la carpeta "docs".


## 3\. Estrategia de Despliegue y Comunicación
En primer lugar, para transferir el código desde el equipo local al servidor de producción se utilizará **SFTP**. Este cifra toda la comunicación mediante **SSH** (puerto 22), garantizando la seguridad de los ficheros. Por otro lado, el **FTP** se descarta por sus vulnerabilidades críticas en entornos reales, ya que este es el tradicional, y transmite datos y credenciales en texto plano.

En segundo lugar, para el flujo de trabajo, el desarrollador se va a encargar de gestionar el código con **Git en local** y una vez haya validado los cambios, los sube al servidor DigitalOcean mediante **SFTP** usando un cliente como **FileZilla** con autenticación por clave SSH.

Por último, mi equipo va a trabajar en **Discord**, una herramienta moderna la cual todos sabemos manejar y sirve para estas ocasiones. Configuraremos **webhooks** que actúa como un “mensajero”,  para recibir alertas automáticas si el servidor cae, permitiendo al equipo reaccionar de inmediato sin revisar manualmente el estado del servidor.
