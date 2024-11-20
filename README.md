# Paso a Paso para ejecutar el proyecto
Lo primero es ejecutar la DataBase en el `Docker`, luego ejecutamos el Backend en `IntelliJ IDEA`, y por ultimo ejecutamos el Frontend en `Visual Studio Code`.

## Ejecutar Docker
#### 1. **Preparar los Archivos**
   - Coloque los archivos `.env`, `Dockerfile` y `docker-compose.yml` en el mismo directorio.
     ```sh
     cd DataBaseAtena
     ```

#### 2. **Construir la Imagen**
   - Utilice el siguiente comando para construir la imagen a partir del `Dockerfile`:
     ```sh
     docker build -t custom-mysql .
     ```

#### 3. **Levantar el Contenedor**
   - Si desea actualizar la configuración o reconstruir la imagen, primero detenga el contenedor con el siguiente comando:
     ```sh
     docker-compose down
     ```
   - Luego, levante el contenedor y reconstruya la imagen utilizando:
     ```sh
     docker-compose up -d --build
     ```

#### 4. **Acceso a MySQL**
   - Después de que el contenedor esté en ejecución, puede acceder a MySQL utilizando el cliente MySQL o cualquier otra herramienta de administración de bases de datos compatible.

#### 5. **Notas Adicionales**

- Asegúrese de que Docker y Docker Compose estén instalados correctamente en su sistema antes de comenzar.
 - Puede personalizar los archivos según los requisitos específicos de su proyecto.

![DOCKER](/ImagenesConfiguracion/Docker.png)

## Ejecutar el Backend

#### 1. **Ingresar**
 - Inicia la carpeta `BackendAtena` en IntelliJ IDEA

#### 2. **Inicio MySQL**
 - Ingrese a Mysql y inicie un nueva conexión como la siguiente imagen
 - **Username** = root
 - **clave** = abcd1234

 ![MySQL](/ImagenesConfiguracion/MySQL.png)

#### 3. **Crear la DataBase**
 - Cree una base de datos llamada `Biblioteca`
    ```sh
     CREATE DATABSE Biblioteca;
     ```
![DATABSE](/ImagenesConfiguracion/CREATE%20DATABASE.png)

#### 4. **Ejecutar el Backend**
 - Ejecute el Backend en IntelliJ IDEA dar click en `BackendBibliotecaApplication`
![DATABSE](/ImagenesConfiguracion/Backend.png)

## Ejecutar el Frontend
#### 1. **Ingresar**
 - Inicia la carpeta `FrontendBiblioteca` en Visual Studio Code
     ```sh
     cd FrontendBiblioteca
     ```
![FRONTEND](/ImagenesConfiguracion/Frontend.png)

#### 2. **Insatal las Dependencias**
 - En la terminal de Visual Studio Code escribe el comando para instalar las dependencias de node
     ```sh
     npm install
     ```
 - Luego en la terminal de Visual Studio Code escribe el comando para instalar las dependencias de axios
      ```sh
     npm install axios
     ```
 - Luego en la terminal de Visual Studio Code escribe el comando para instalar las dependencias de Android Studio
      ```sh
     npm install @capacitor/android
     npx cap add android
     ionic build
     npx cap ls
     npx cap copy android
     npx cap open android     
     ```

#### 3. **Configuración Puerto**
 - En los ports de Visual Studio Code inicia con el puerto 9090, y ponlo como publico, como se visualiza en la siguiente imagen

![PUERTO](/ImagenesConfiguracion/Puerto.png)

#### 4. **Ejecuta**
 - En la terminal de Visual Studio Code Escribe el comando de inicializar
     ```sh
     ionic serve
     ```
 - Automáticamente el proyecto se inicializa en el navegador o ingresa en el navegador el siguiente enlace
     ```sh
     http://localhost:8100/home
     ```
![FRONTEND](/ImagenesConfiguracion/ionic%20serve.png)

## PROYECTO
 - Listo, el proyecto se se habrá inicializado y en su navegador se vera de la siguiente forma

![PROYECTO](/ImagenesConfiguracion/Home.png)

 - Y con la APK en android se vera de la siguiente manera

![PROYECTO](/ImagenesConfiguracion/HomePage.png)

### ARREGLOS DEL TRABAJO
 - Se arreglo la visualizacion y se agrego un atributo de `dias`, el cual gestiona los Dias de prestamos de los libros llevados por los Clientes.

![PRESTAMOS](/ImagenesConfiguracion/Prestamos.png)
![PRESTAMOS](/ImagenesConfiguracion/PrestamosAndroid.png)
