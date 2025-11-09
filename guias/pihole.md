# 🔧 Instalación de Pi-hole + iptables

## 🎯 Objetivo
Configurar Pi-hole como filtro DNS para red local.

## 📋 Requisitos
- Ubuntu Server
- 2 interfaces de red
##Configurar iptables
sudo iptables -A FORWARD -i enp0s8 -o enp0s3 -j ACCEPT
sudo iptables -A FORWARD -i enp0s3 -o enp0s8 -m state --state ESTABLISHED,RELATED -j ACCEPT
sudo iptables -t nat -A POSTROUTING -o enp0s3 -j MASQUERADE
## 🚀 Instalación

### Descargar Pi-hole
```bash
curl -sSL https://install.pi-hole.net | bash
