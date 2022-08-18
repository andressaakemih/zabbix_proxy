# Instalação Zabbix Proxy

Comandos:

### wget https://repo.zabbix.com/zabbix/5.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_5.0-1+focal_all.deb

### dpkg -i zabbix-release_5.0-1+focal_all.deb

### apt update

### apt search zabbix-proxy

// escolha a versão major compartível com seu zabbix-server (zabbix-server: 5.0 == zabbix-proxy: 5.0)

### apt install zabbix-proxy-sqlite3

### vi /etc/zabbix/zabbix_proxy.conf

// editar as informações:
// Server= (IP_servidor)
// Hostname= (nome_proxy)
// DBName= (caminho_BD_proxy) {ex: /tmp/zabbixdb}

### systemctl restart zabbix-proxy

// será criado o banco do proxy


Após o passo a passo de instalação:

Cadastrar o Proxy no front-end do Zabbix:
    
- Administração → Proxies 
    
- Nome do proxy == Hostname (configurado no arquivo: zabbix_proxy.conf)
    
Cadastrar o Proxy para monitorar
    
- Template → Template App Zabbix Proxy