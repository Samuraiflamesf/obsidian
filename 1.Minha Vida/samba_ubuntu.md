---
Title: Tutorial do Samba no UbuntuServer
created: 2024-06-14
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/web
  - git
---
| [Voltar](index) |
#### Instalando
```
sudo apt-get install samba
```
#### Configurando
```
sudo nano /etc/samba/smb.conf
```
#### Estrutura
```
[NomePasta]
comment = nomepasta
path = /.caminho
read only = no
browsable = yes
```
#### Reinicia o samba
```
sudo service smbd restart
```
#### Colocando uma senha
```
sudo smbpasswd -a user
```
### References
1. https://www.youtube.com/watch?v=NJ_TMShpsZw
  