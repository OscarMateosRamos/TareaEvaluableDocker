# Ejercicio 3 - Contenedores en Red Adminer y MariaBD

1. Crea una red bridge redbd
    
    ```bash
    docker network create --driver bridge redbd
    ```
    
    ![image.png](image.png)
    
2. Crea un contenedor con una imagen de
mariaDB que estará en la red
redbd. Este contenedor se ejecutará en segundo plano, y será accesible a través del puerto 3306. (Es necesario definir la contraseña del usuario root y un volumen de datos persistente)
    
    
    ```bash
    docker run -d --name mariadb-container --network redbd -e MYSQL_ROOT_PASSWORD=123 -v mariabd_data:/var/lib/mysql -p 3306:3306 mariadb:latest
    
    ```
    
    ![image.png](image%201.png)
    
    Comprobamos que el contenedor se creo correctamente haciendo un docker ps
    
    ![image.png](image%202.png)
    
3. Crear un contenedor con Adminer o con phpMyAdminque se pueda conectar alcontenedor de la BD
    
    
    ```bash
    docker run -d --name adminer-container --network redbd -p 8080:8080 adminer:latest
    ```
    
    ![image.png](image%203.png)
    
    Comprobamos que el contenedor se creo correctamente haciendo un  docker ps
    
    ![image.png](image%204.png)
    
4. Desde la interfaz gráfica, crear una base de datos y una tabla en el servidor de base de
datos
    
    ![image.png](image%205.png)
    
    ![image.png](image%206.png)
    

![image.png](image%207.png)

Eliminamos los contedores utilizados usando docker rm  y el nombre del contendor si el contenedor que  queremos borrar esta en ejecucion deberemos hacer un docker stop y el nombre del contendor

```bash
docker stop adminer-container
```

![image.png](image%208.png)

```bash
docker rm adminer-container
```

![image.png](image%209.png)

```bash
docker stop mariadb-container
```

![image.png](image%2010.png)

```bash
docker rm mariadb-container
```

![image.png](image%2011.png)