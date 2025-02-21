# Ejercicio 2  - Servidor de base de datos

# Ejercicio 2  - Servidor de base de datos

1. Abre Docker Desktop. Busca mariadb en la sección de imágenes. Selecciona la imagen
oficial. Descárgala si no la tienes.

![image.png](image.png)

![image.png](image%201.png)

1. Despliega un contenedor utilizando esa imagen. Características:
- **Nombre del contenedor:** bbdd.
- **Puerto:** 3306 - debe poder conectarse externamente.
- **Utiliza un volumen llamado** datos-mariadb.
- **Usa las variables de entorno necesarias para que:**
    - **El usuario root tenga la contraseña:** base.
    - **La base de datos por defecto sea:** daw.
    - **Se cree un usuario:** daw, con la contraseña password.
    
    ![image.png](image%202.png)
    

![image.png](20d76237-223e-41bf-a675-ee4685158f61.png)

1. Arranca el contenedor

![image.png](image%203.png)

4.Accede a la base de datos usando una herramienta gráfica, como, por ejemplo

dbeaver. Conéctate con el usuario daw. Crea una base de datos y alguna tabla.

![image.png](image%204.png)

![image.png](image%205.png)

![image.png](image%206.png)

1. Borra el contenedor

![image.png](image%207.png)

 6. Ver en Docker Desktop que el volumen que contiene los datos no se ha borrado

![image.png](image%208.png)

1. Crear otro contenedor con un servidor de base de datos que use el mismo volumen.
Llamar al contenedor bbdd-2. Comprobar que la base de datos y la tabla creada
anteriormente siguen ahí.

![image.png](image%209.png)

Despues de volverme a conectar a la base de dartos, puedo ver que sigue ahi la tabla 

![image.png](image%2010.png)

1. Intenta borrar la imagen de mariadb ¿Qué sucede?

Docker no  permite eliminar la imagen porque aún hay contenedores asociados con ella. Debería detener y eliminar todos los contenedores que utilizan esa imagen antes de poder eliminar la imagen.

![image.png](image%2011.png)

![image.png](image%2012.png)

![image.png](image%2013.png)

![image.png](image%2014.png)

En este orden, podemos ver que hemos borrado la imagen con éxito

![image.png](image%2015.png)