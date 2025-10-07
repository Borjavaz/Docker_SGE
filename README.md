# Docker_SGE

---

## 1. Descargar la imagen "alpine" sin arrancarla y comprobar que está en el equipo  


### Con el pull la descargamos

```bash
docker pull alpine
```

<img width="733" height="217" alt="image" src="https://github.com/user-attachments/assets/3b909ac8-0745-4294-93fc-454da88c6db8" />  

### Con el images realizamos la comprobacion  

```bash
docker images
```  
<img width="566" height="113" alt="image" src="https://github.com/user-attachments/assets/fc1672e1-910d-4a0f-9eb4-f739bd6cefb2" />

---

## 2. Crear un contenedor sin nombre.

### Para crear un contenedor (sin nombre) utilizamos el siguiente comando:

```bash
docker run alpine
```
<img width="819" height="235" alt="image" src="https://github.com/user-attachments/assets/f880fcbc-8eee-41c0-b622-a5060172599b" />

El contenedor va a asignar un nombre aleatorio al contenedor.


### Para comprobar el nombre utilizamos el siguiente comando:

```bash
docker ps -a
```
<img width="1100" height="118" alt="image" src="https://github.com/user-attachments/assets/d914edc7-f9b5-44df-b19f-371a79f45e6b" />

Como podemos ver en esta imagen:
* El nombre que se le asigno al contenedor es:  **zealous_meninsky**
* Como podemos ver en el apartado status, el contenedor no esta arrancado

---

## 3. Crear un contenedor con el nombre `dam_alp1`. 

#### Con el siguiente comando creamos el contenedor dam_alp1 y lo iniciamos directamente, ademas ya estamos dentro de el.

```bash
docker run -it --name dam_alp1 alpine
```

<img width="873" height="147" alt="image" src="https://github.com/user-attachments/assets/d69b45ca-9d88-4634-9ec6-c9fc32d87e87" />

En esta imagen podemos ver como se creo el contenedor en la aplicacion, el punto de color verde quiere decir que el contenedor se esta corriendo. Ademas el, "/ #" en la terminal quiere decir que nos encontramos dentro del contenedor.

#### Si el contenedor esta corriendo, puedes entrar con el siguiente comando.

<img width="873" height="147" alt="image" src="https://github.com/user-attachments/assets/b9a80823-22d0-4b39-9bc8-4f2c8239b2da" />

```bash
docker exec -it dam_alp1 sh
```
---

## 4. Comprobar la IP y conectividad.

#### Primero utilizamos el comando de antes para entrar en el contenedor ya creado: *dam_alp1*

```bash
docker exec -it dam_alp1 sh
```
#### A continuacion utilizamos el comando **ip addr** para comprobar la ip del contenedor.

```bash
ip addr
```
Nos devuelve muchos apartados, pero el más importante es el ultimo que nos dice la ip

<img width="790" height="119" alt="image" src="https://github.com/user-attachments/assets/b42433eb-4386-4805-8d31-7acaca2e14c2" />

En este caso la IP es : ***172.17.0.2/16***

#### Para comprobar la conexion con google.com utilizamos el siguiente comando:

```bash
ping -c 3 google.com
```

`-c 3` indica que solo se enviarán 3 paquetes y luego el comando se detendrá.

<img width="527" height="226" alt="image" src="https://github.com/user-attachments/assets/f8196a6e-64e5-4c43-b936-d48302ddb26a" />

Como se puede ver en la imagen la conecxion se realizo correctamente

---

## 5. Creacion del contenedor dam_alp2

#### Con este comando creamos el contenedor:

```bash
docker run -it --name dam_alp2 alpine
```

<img width="805" height="151" alt="image" src="https://github.com/user-attachments/assets/244c6290-87ea-4066-aa49-17daedbc95d4" />

`-it` sirve para crear el contenedor e iniciarlo.Como se puede ver en la captura esta iniciado.

#### Comando para entrar en el contenedor cuando ya esta iniciado

```bash
docker exec -it dam_alp2 sh
```

<img width="796" height="143" alt="image" src="https://github.com/user-attachments/assets/5b53c51f-945c-4fec-a7c2-fdfe9789d1b1" />

## 5.1 Hacer ping entre dos contenedores

## Primero verificamos la IP de uno de los contenedores, en este caso de dam_alp1 con el siguiente comando:

```bash
docker exec dam_alp1 ip addr
```

<img width="809" height="399" alt="image" src="https://github.com/user-attachments/assets/25177012-e3fd-448e-8790-667ca5a06b99" />

Como se puede ver en la captur ala IP es: ***172.17.0.3***

## Ahora nos metemos en el otro contenedor y hacemos ping con este comando:

```bash
ping -c 3 172.17.0.3
```

<img width="814" height="476" alt="image" src="https://github.com/user-attachments/assets/0e483665-050c-4c53-8be2-5f1ada84af85" />

Como se puede ver en la captura si que se puede hacer ping entre los contenedores siempre que esten los dos activos.

---

## 6. Salir del terminal

## Para salir del termilan utilizamos el comando:

```bash
exit
```
<img width="803" height="304" alt="image" src="https://github.com/user-attachments/assets/8841d19c-8cde-4e0e-b7eb-9e0158ea4b87" />

Para saber el estado de los contenedores utilizamos el comando:

```bash
docker ps -a
```

<img width="996" height="415" alt="image" src="https://github.com/user-attachments/assets/601b0492-2bd0-4158-9651-23ac51745f77" />

Como podemos ver en la captura los contenedores siguen acticos desde hace 10 y 5 minutos.




