# README - Automatización de Infraestructura Digital

**Nombre del estudiante:** Christian Geovanni Arredondo Rangel  
**Unidad:** Unidad I - Entornos de desarrollo en la automatización de redes  
**Fecha:** 11 de Junio del 2025

---

## 📑 Índice

- [1. Instalación de herramientas necesarias](#1-instalación-de-herramientas-necesarias)
- [2. Instalación de Docker Engine](#2-instalación-de-docker-engine)
- [3. Instalación de Docker Compose](#3-instalación-de-docker-compose)
- [4. Instalación de Git](#4-instalación-de-git)
- [5. Pruebas de funcionamiento](#5-pruebas-de-funcionamiento)
- [6. Ejecución de archivo YML](#6-ejecución-de-archivo-yml)
- [7. Conclusión](#7-conclusión)
- [8. Bibliografía](#8-bibliografía)

---

## 1. Instalación de herramientas necesarias

### Visual Studio Code

```bash
sudo snap install code --classic
```

> Instala el editor de código Visual Studio Code desde Snap.


![VSCode instalación](images/capture1.png)
![VSCode instalación](images/capture2.png)
![VSCode instalación](images/capture3.png)
![VSCode instalación](images/capture4.png)

### Extensiones de VSCode desde terminal

```bash
code --install-extension ms-azuretools.vscode-docker
code --install-extension redhat.vscode-yaml
code --install-extension eamodio.gitlens
```

> Estas extensiones permiten trabajar mejor con Docker, archivos YAML y control de versiones.


---

## 2. Instalación de Docker Engine

### Paso 1: Actualizar sistema

```bash
sudo apt update
sudo apt upgrade -y
```


![Docker Engine paso](images/capture5.png)
![Docker Engine paso](images/capture6.png)



### Paso 2: Instalar dependencias

```bash
sudo apt install ca-certificates curl gnupg lsb-release -y
```
![Docker Engine paso](images/capture8.png)
### Paso 3: Agregar la clave GPG de Docker
![Docker Engine paso](images/capture9.png)

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

### Paso 4: Agregar repositorio oficial de Docker
![Docker Engine paso](images/capture10.png)

```bash
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Paso 5: Instalar Docker Engine
![Docker Engine paso](images/capture11.png)

```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

### Permitir uso de Docker sin sudo
![Docker Engine paso](images/capture12.png)

```bash
sudo usermod -aG docker $USER
newgrp docker
```

---

## 3. Instalación de Docker Compose

Docker Compose ya viene como plugin desde Docker 20.10+.

### Verifica versión de la distribución

```bash
lsb_release -a
```

![Docker Compose verificación](images/capture13.png)

### Verifica versión del plugin

```bash
docker compose version
```

---

## 4. Instalación de Git

### Actualizar repositorios

```bash
sudo apt update
```

### Instalar Git

```bash
sudo apt install git -y
```

![Git instalación](images/capture14.png)


### Configuración inicial de Git

```bash
git config --global user.name "Christian Geovanni Arredondo Rangel"
git config --global user.email "chriatiangeovanniarredondorang@gmail.com"
```

> Estos comandos configuran tu identidad global en Git.
![Git instalación](images/capture15.png)
![Git instalación](images/capture16.png)


---

## 5. Pruebas de funcionamiento

### Verificar instalación de Docker

```bash
sudo docker run hello-world
```

![Hello World Docker](images/capture17.png)


> Si aparece el mensaje "Hello from Docker!", la instalación fue exitosa.

---

## 6. Ejecución de archivo YML

### docker-compose.yml de prueba

```yaml
version: '3.8'

services:
  web:
    image: nginx:alpine
    ports:
      - "8080:80"
```
![Hello World Docker](images/capture18.png)

### Ejecutar el contenedor

```bash
docker compose up -d
```
![Hello World Docker](images/capture19.png)

> Accede a `http://localhost:8080` o `http://<IP-del-servidor>:8080` para verificar.

![Hello World Docker](images/capture20.png)

> Revisamos que el contenedro este en ejecucion con el comando:
```bash
docker ps
```
![Hello World Docker](images/capture21.png)

Para detener y eliminar los contenedores:

```bash
docker compose down
```

---

## 7. Conclusión

Mi nombre es Christian Geovanni Arredondo Rangel, y a lo largo de esta unidad aprendí y apliqué herramientas clave para la automatización de infraestructura, con un enfoque práctico en entornos basados en contenedores. Uno de los hallazgos más relevantes fue la transición del manejo manual de contenedores hacia un enfoque automatizado usando herramientas como Docker Compose, lo cual representa una mejora significativa en eficiencia y organización.

Previamente, al crear contenedores con Docker, era necesario ejecutar una serie de comandos individuales, definir variables manualmente y controlar cada componente por separado. Este proceso, aunque funcional, implicaba una carga operativa considerable. Con Docker Compose, logramos simplificar estas tareas mediante la definición de archivos `.yml`, lo que permite levantar múltiples servicios con una sola instrucción, gestionar puertos, volúmenes y redes de forma declarativa y replicable.

La automatización no solo reduce el margen de error humano, sino que nos permite dedicar más tiempo al diseño y desarrollo de nuevas soluciones tecnológicas. Comprender y aplicar estas herramientas representa un paso fundamental para cualquier profesional que busque optimizar su entorno de desarrollo y responder con agilidad a los desafíos actuales de la ingeniería de redes y software.

---

## 8. Bibliografía

Docker Inc. (2025). *Docker documentation*. Recuperado de https://docs.docker.com/  
Docker Inc. (2025). *Docker Compose documentation*. Recuperado de https://docs.docker.com/compose/  
Docker Inc. (2025). *Docker Swarm documentation*. Recuperado de https://docs.docker.com/engine/swarm/  
Microsoft. (2025). *Visual Studio Code documentation*. Recuperado de https://code.visualstudio.com/docs  
OpenSSH. (2025). *OpenSSH documentation*. Recuperado de https://www.openssh.com/manual.html  
The Git Project. (2025). *Git documentation*. Recuperado de https://git-scm.com/doc  
Ubuntu. (2025). *Ubuntu documentation*. Recuperado de https://ubuntu.com/docs  
YAML Ain't Markup Language (YAML). (2025). *YAML documentation*. Recuperado de https://yaml.org/