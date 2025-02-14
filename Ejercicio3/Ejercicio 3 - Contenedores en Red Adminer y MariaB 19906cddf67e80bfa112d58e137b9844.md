# Ejercicio 3 - Contenedores en Red Adminer y MariaBD

1. Crea una red bridge redbd
    
    ```bash
    docker network create redbd
    ```
    
    ![image.png](image.png)
    
2. Crea un contenedor con una imagen de
mariaDB que estará en la red
redbd. Este contenedor se ejecutará en segundo plano, y será accesible a través del puerto 3306. (Es necesario definir la contraseña del usuario root y un volumen de datos persistente)
    
    
    ```bash
    docker run -d --name mariabd-container ^ --network redbd ^ -e MYSQL_ROOT_PASSWORD=123 ^ -v mariabd_data: /var/lib/mysql ^ -p 3306:3306 ^ mariadb:latest
    ```
    
    ![image.png](image%201.png)
    
3. Crear un contenedor con Adminer o con phpMyAdminque se pueda conectar alcontenedor de la BD
    
    
    ```bash
    docker run -d --name adminer-container ^ --network redbd ^ -p 8080:80808 ^ adminer:latest
    ```
    
    ![image.png](image%202.png)
    
4. Desde la interfaz gráfica, crear una base de datos y una tabla en el servidor de base de
datos
    
    ![image.png](image%203.png)
    
    ![image.png](image%204.png)
    

![image.png](image%205.png)