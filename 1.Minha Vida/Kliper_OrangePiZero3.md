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
- Crowsnest, select (8).
Agora, você deve conseguir acesso remoto ao seu Orange Pi por meio da Internet usando seu endereço IP.

# Configurando os arquivos no Mainsail
![[VS--YouTube-HowtoUpgradetoKlipperonanyEnder3forHighPerformance-15’48”.webp]]
Para minha impressora Ender, com placa CR V4.2.2, preciso localizar o arquivo de configuração `printer.cfg` e copiá-lo para a pasta `Machine/Config Files`.
Você pode encontrar o arquivo `printer.cfg` em seu repositório personalizado:
* [My_Ender_3](https://github.com/Samuraiflamesf/My_Ender_3)
Caso você tenha uma impressora diferente, consulte o repositório oficial do Klipper:
* [Klipper3d/klipper](https://github.com/Klipper3d/klipper/tree/master/config)
Agora esse processo é especifico para minha placa:
## **Configurar o Klipper:**
**Navegar para o Diretório do Klipper:**
```
cd ~/klipper
make menuconfig
make
```
![[Pasted image 20250115180327.webp]]
1. **Obtenha o arquivo gerado pelo FileZilla:**
   - Acesse o diretório onde o arquivo foi gerado.
   - /home/orangepi/klipper/out/klipper.bin
2. **Transfira o arquivo para o cartão Micro SD:**
   - Insira o cartão Micro SD em um leitor de cartão.
   - Copie o arquivo do computador para o cartão Micro SD.
3. **Insira o cartão Micro SD no Ender:*
4. **Verifique a porta serial utilizada:**
   - No terminal da impressora, execute o comando:
     ```
     ls /dev/serial/by-id/*
     ```
5. **Altere o trecho no código do printer.cfg:**
   - Abra o arquivo `printer.cfg` em um editor de texto.
	```
	[mcu]
	serial: /dev/serial/by-id/usb-1a86_USB_Serial-if00-port0
	```
6. **Salve o arquivo printer.cfg e reinicie a impressora:**
   - Salve o arquivo `printer.cfg`.
   - Reinicie a impressora para que as alterações entrem em vigor.

### Referências
1. [Angry IP](https://angryip.org/download/#windows) 
2. [OrangePi Zero 3 ISO](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/service-and-support/Orange-Pi-Zero-3.html)
3. [Balena Etcher](https://etcher.balena.io/)
4. [Kiauh](https://github.com/dw-0/kiauh) 
5. [How to Upgrade to Klipper on any Ender 3 for High Performance - YouTube](https://www.youtube.com/watch?v=N41JY1Gukuk&t=495s)
6. [How to Install Klipper On Anycubic Kobra Go/Neo - OrangePi Zero 3 - YouTube](https://www.youtube.com/watch?v=A5WO4nwDzsU&t=1136s)
7. [Orange Pi 3 LTS OctoPrint + Webcam - Guia Completo para Iniciantes : r/octoprint](https://www.reddit.com/r/octoprint/comments/11rjjji/orange_pi_3_lts_octoprint_webcam_beginners/?tl=pt-br)
  