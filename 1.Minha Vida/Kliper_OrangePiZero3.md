---
title: Kliper_OrangiPiZero3
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/web
---
| [Voltar](index) |
Para OrangePi Debian:
username: orangepi 
password: orangepi
```
ssh orangepi@ip
```

Codigo par acolocar no terminal
```
sudo nmcli radio wifi on
```
```
sudo nmcli device wifi list
```
```
sudo nmcli device wifi connect "Nome" password
```
```
sudo nmcli connection show
```
```
sudo apt-get update && sudo apt-get install git -y
```
```
cd ~ && git clone https://github.com/dw-0/kiauh.git
```
```
./kiauh/kiauh.sh
```
Agora vai coloca para installar, klipper com recommended. E enter para instalar
Depois instalar Moonraker, com Y
Depos instalar mainsail, com macros
Depois de instalar tudo rodar:
```
cd ~/klipper
```
```
make menuconfig
```
```
make
```
```
ls /dev/serial/by-id/*
```


### Referências
1. [Angry IP](https://angryip.org/download/#windows) 
2. [OrangePi Zero 3 ISO](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/service-and-support/Orange-Pi-Zero-3.html)
3. [Balena Etcher](https://etcher.balena.io/)
4. [Kiauh](https://github.com/dw-0/kiauh) 
5. [Klipper4KobraGoNeo](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbllKZmFYUmFUNFZKUDMzQk9GbURFWUc4eEd2QXxBQ3Jtc0tsbXU1UlgwNWt4Q3BGQ0h6WXV0ZmlRLWR4aFBvTnRTVDd0cUpfdm1XLWpWXzlyQTdTTVFNSXN4YjJhMmRrMVB5aG12blFiUlNsdnJiSU9pTXRFaGhGRm43XzE2NEpzWUNBN2Y2VWFjWU1oVEJTeWNzRQ&q=https%3A%2F%2Fgithub.com%2F1coderookie%2FKlipper4KobraGoNeo&v=A5WO4nwDzsU)
6. [How to Upgrade to Klipper on any Ender 3 for High Performance - YouTube](https://www.youtube.com/watch?v=N41JY1Gukuk&t=495s)
7. [How to Install Klipper On Anycubic Kobra Go/Neo - OrangePi Zero 3 - YouTube](https://www.youtube.com/watch?v=A5WO4nwDzsU&t=1136s)
  