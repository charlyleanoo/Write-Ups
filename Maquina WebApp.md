
## Summary

Nmap:
Nmap, or Network Mapper, is a network scanning tool that's used for a variety of purposes.

wpscan:
WordPress Security Scanner.
## Description

Encontramos que esta es la maquina que tenemos que atacar con la ip 192.168.56.101

![[Pasted image 20240916173416.png]]

![[Pasted image 20240916211729.png]]

![[Pasted image 20240916211856.png]]

![[Pasted image 20240916212913.png]]


![[Pasted image 20240916223549.png]]

![[Pasted image 20240916225931.png]]
![[Pasted image 20240919123250.png]]

![[Pasted image 20240919123358.png]]
	wpscan --url https://192.168.56.101:12380/blogblog/wp-login.php/ -U john -P /usr/share/wordlists/rockyou.txt --disable-tls-checks

![[Pasted image 20240919131516.png]]



![[Pasted image 20240917082601.png]]

![[Pasted image 20240924163126.png]]

![[Pasted image 20240924163152.png]]

![[Pasted image 20240924215307.png]]

![[Pasted image 20240924215331.png]]

![[Pasted image 20240924215948.png]]


![[Pasted image 20240924215620.png]]


![[Pasted image 20240924215751.png]]

## Steps

Primero encontramos su pagina web en el puerto  `12380` después buscamos su `robots.txt` que nos lleva a su WordPress , a partir de ahí usamos `wpscan` para saber directorios y usuarios.
Con esto obtuvimos usuarios y escogimos a `john` y le hacemos otro wpscan con `rockyou.txt` para sacar su contraseña que nos dio que fue `succesful` y su contraseña es ==`incorrect`==, con esto entramos a WordPress y tenemos que subir un plug in con un `reverse Shell` creado en reverse Shell generator.
De de aquí sacamos el historial de comandos donde esta configurado un usuario con su contraseña para `ssh` ya teniendo esto entramos por ssh como `Peter`, corremos el comando ==`sudo /bin/bash`== y nos hacemos root y buscamos la `flag.txt` y la encontramos.



## Extra Material

https://www.revshells.com/


https://wp.geohome.com/wp-login.php


wpscan --url https://192.168.56.101:12380/blogblog -e vp,vt,u1-5,m1-15 --api-token 9lc4R9fkwWyGs53BUkTLb8PVlXQBaadb4lWB9LOsZmk --disable-tls-checks