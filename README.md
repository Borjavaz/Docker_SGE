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





