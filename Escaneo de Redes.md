#linux #nmap #redes

-> Identificar host puertos y servicios
-> descubrir maquinas activas
-> identificar sistema operativo
-> direcciones ips accesibles
-> arquitectura del sistema operativo
-> puertos y servicios que se ejecutan

- 80 - http
- 443 - http
- 22 - ssh
- 21 - ftp
- 3306 - sql
- 3389 - rdp 

# Tipos de escaneo

- escaneo de puertos
- escaneo de red
- escaneo de vulnerabilidades7

# NMAP:

nmap <opciones><ip/hostname objetivo>

escáner de seguridad para explorar redes
administra inventarios de red y monitorea el tiempo de actividad

sudo nmap -p --min-rate 5000 <ip>

sudo nmap -p80,443,8080 --min-rate 5000 <ip>

sudo nmap -sVF -p- --min-rate 5000 <ip>

sudo nmap -p- -sV --min-rate 5000 <ip>

sudo nmap -p- -sV --script vuln --min-rate 5000 <ip>

sudo nmap -p- -sV -O -A --script vuln --min-rate 5000 <ip>

sudo nmap -p- --open --min-rate 5000 -Pn -n -sV -sS -vvv $(cat target.txt)

Extras

Advanced Port Scanner

tarea: free proxies, vpn, spoofing MAC

hydra -l zoe -P /path/to/passwordlist.txt ssh://192.168.56.101

medusa -h 192.168.56.101 -u zoe -P /path/to/passwordlist.txt -M ssh

python3 ssh_enum.py 192.168.56.101 -U /home/charly/Desktop/usernames.txt --bytes 50000 --samples 12 --trials 1 

python3 ssh_enum.py 192.168.56.101 -u RED --bytes 50000 --samples 12 --trials 1

wfuzz -c --hc=500,404 -w /usr/share/wordlists/rockyou.txt http://192.168.56.101/FUZZ

wpscan --url https://192.168.56.101:12380/blogblog -e vp,vt,u1-5,m1-15 --api-token 9lc4R9fkwWyGs53BUkTLb8PVlXQBaadb4lWB9LOsZmk --disable-tls-checks


