# ProjetodeRoteamentoEstatico

RT-01

enable
configure terminal
hostname RT-01
login block-for 3 attempts 3 within 1
banner motd "ACESSO APENAS PARA PESSOAS AUTORIZADAS"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username ruthbraga privilege 15 secret Batata
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface Serial 0/0/1
ip address 200.200.100.0 255.255.255.252 
no shutdown
exit
interface serial 0/0/0
ip address 200.200.100.4 255.255.255.252
no shutdown
interface gigabitEthernet 0/0
ip address 192.168.1.0 255.255.255.224
no shutdown
do wr
exit



RT-02

enable
configure terminal
hostname RT-02
login block-for 3 attempts 3 within 1
banner motd "ACESSO APENAS PARA PESSOAS AUTORIZADAS"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username ruthbraga privilege 15 secret Batata
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface Serial 0/0/1
ip address 200.200.100.0 255.255.255.252 
no shutdown
exit
interface serial 0/0/0
ip address 200.200.100.12 255.255.255.252
no shutdown
interface gigabitEthernet 0/0
ip address 10.40.10.0 255.255.240.0
no shutdown
do wr
exit

RT-03

enable
configure terminal
hostname RT-03
login block-for 3 attempts 3 within 1
banner motd "ACESSO APENAS PARA PESSOAS AUTORIZADAS"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username ruthbraga privilege 15 secret Batata
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface Serial 0/0/0
ip address 200.200.100.4 255.255.255.252 
no shutdown
exit
interface serial 0/0/1
ip address 200.200.100.8 255.255.255.252
no shutdown
interface gigabitEthernet 0/0
ip address 192.168.0.0 255.255.255.128
no shutdown
do wr
exit

RT-04

enable
configure terminal
hostname RT-04
login block-for 3 attempts 3 within 1
banner motd "ACESSO APENAS PARA PESSOAS AUTORIZADAS"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username ruthbraga privilege 15 secret Batata
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface Serial 0/0/0
ip address 200.200.100.12 255.255.255.252 
no shutdown
exit
interface serial 0/0/1
ip address 200.200.100.8 255.255.255.252
no shutdown
interface gigabitEthernet 0/0
ip address 172.16.42.0 255.255.254.0
no shutdown
do wr
exit

SW-01

enable
configure terminal
hostname SW-01
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username ruthbraga privilege 15 secret bolo
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
interface vlan 1
ip address 192.168.8.254 255.255.255.224
description INTERFACE DE GERENCIAMENTO
no shutdown
exit
ip default-gateway 192.168.8.1
do wr


SW-02

enable
configure terminal
hostname SW-02
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username ruthbraga privilege 15 secret bolo
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
interface vlan 1
ip address 10.40.23.254 255.255.255.240
description INTERFACE DE GERENCIAMENTO
no shutdown
exit
ip default-gateway 10.40.23.1
do wr

SW-03

enable
configure terminal
hostname SW-03
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username ruthbraga privilege 15 secret bolo
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
interface vlan 1
ip address 192.168.0.0 255.255.255.128
description INTERFACE DE GERENCIAMENTO
no shutdown
exit
ip default-gateway 192.168.0.1
do wr

SW-04

enable
configure terminal
hostname SW-04
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username ruthbraga privilege 15 secret bolo
username estagiario privilege 1 secret senha
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
interface vlan 1
ip address 172.16.42.0 255.255.254.0
description INTERFACE DE GERENCIAMENTO
no shutdown
exit
ip default-gateway 172.16.42.1
do wr

