# LICENCIAS DE LA INFRAESTRUCTURA 

## 1. Apache Guacamole

Gateway de escritorio remoto sin cliente, requerido por el enunciado.

**Licencia:** Apache License, Version 2.0
**Fuente:** https://guacamole.apache.org/open-source/

## 2. OpenSSH — linuxserver/openssh-server:latest

Imagen usada por el servicio servidor_ssh (puerto 2222).

### OpenSSH
**Licencia:** BSD/OpenSSH License
**Fuente:** https://github.com/openssh/openssh-portable/blob/master/LICENCE

### Imagen Docker
**Licencia:** GNU General Public License v3.0 (GPL-3.0)
**Fuente:** https://github.com/linuxserver/docker-openssh-server


## 3. Docker Engine

Motor que orquesta los contenedores definidos en este compose.

**Licencia:** Apache License 2.0
**Fuente:** https://docs.docker.com/engine/


## 4. LinuxServer Webtop — linuxserver/webtop:ubuntu-xfce

Imagen usada por el servicio servidor_rdp. Proporciona un escritorio accesible desde el navegador.

**Licencia:** GNU General Public License v3.0 (GPL-3.0)
**Fuente:** https://github.com/linuxserver/docker-webtop


## Resumen comparativo

| Componente | Licencia | Tipo |
|---|---|---|
| Apache Guacamole | Apache 2.0 | Permisiva |
| OpenSSH (binario) | BSD/OpenSSH | Permisiva |
| linuxserver/openssh-server (imagen) | GPL-3.0 | Copyleft |
| Docker Engine | Apache 2.0 | Permisiva |
| linuxserver/webtop (imagen) | GPL-3.0 | Copyleft |
