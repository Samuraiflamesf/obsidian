---
title: Instalando o Kliper no Orangi Pi Zero 3 + Webcam Basica
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/web
---
| [Voltar](index) |
# Download e Instalação da ISO
Para obter a imagem ISO, visite o site oficial da Orange Pi: [Orange Pi - Orangepi](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/service-and-support/Orange-Pi-Zero-3.html).
- Selecione a distribuição "debian" com o kernel 6.1 e baixe a versão `debian server`.
- Para instalar a imagem ISO no cartão de memória, use a ferramenta balenaEtcher. 
- Siga as instruções no site oficial do balenaEtcher para concluir a instalação.
# Configuração para OrangePi Debian
**Credenciais de Acesso:**
```
ssh orangepi@ip
```
- Usuário: orangepi
- Senha: orangepi
# Comandos para habilitar Wi-Fi
**Habilitar Wi-Fi:**
```
sudo nmcli radio wifi on
sudo nmcli device wifi list
```
**Conectar à Rede Wi-Fi:**
```
sudo nmcli device wifi connect "My House" password naoseiasenha
sudo nmcli connection show
```
**Verificar seu endereço IP usando**
```
nmcli device show wlan0 | grep IP4.ADDRESS
```
### Atualizar e Instalar o git:
```
sudo apt-get update && sudo apt-get install git -y
```
## Executar o Instalador Kiauh:
```
cd ~ && git clone https://github.com/dw-0/kiauh.git
./kiauh/kiauh.sh
```
![[Pasted image 20250115152247.webp]]
- Klipper com "Recommended", select (1)
- Moonraker (Y), select (2)
- Mainsail com Macros, select (3)
- Crowsnest, select (8)
## **Configurar o Klipper:**
**Navegar para o Diretório do Klipper:**
```
cd ~/klipper
make menuconfig
make
```
**Listar Portas Seriais:**
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
8. [Orange Pi 3 LTS OctoPrint + Webcam - Guia Completo para Iniciantes : r/octoprint](https://www.reddit.com/r/octoprint/comments/11rjjji/orange_pi_3_lts_octoprint_webcam_beginners/?tl=pt-br)
  