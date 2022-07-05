## [TEAMPASS] - Cofre de Senhas

O Teampass é uma ferramenta para armazenamento de senhas de código aberto e fácil instalação 

### Instalando e Configurando

~~~ServidorXAMPP
Caso queira instalar o XAMPP, segue:
#wget http://sourceforge.net/projects/xampp/files/XAMPP%20Linux/5.5.30/xampp-linux-x64-5.5.30-0-installer.run
Adicionar permissão 755 (rwxr-xr-x)
#chmod 755 xampp-linux-x64-5.5.30-0-installer.run
Executar instalador:
#./xampp-linux-blablabla-installer.run 
Fonte de instalação do XAMPP
http://www.vivaolinux.com.br/artigo/Como-instalar-o-XAMPP-no-GNULinux
~~~

~~~ServidorLAMP
Para iniciar a instalação e configuração, é necessário ter um servidor LAMP (Linux+Apache+MySQL+PHP) instalado. Para isso vamos utilizado o comando abaixo:
#apt-get install apache2 php5 mysql-client mysql-client-5.5 mysql-server mysql-server-5.5 -y
~~~

*Após instalar o LAMP ou XAMPP e antes de começar a instalar e configurar o TEAMPASS, é necessário criar a base de dados do teampass. Esta por sua vez, será populada durante a instalação.

```markdown
Criar base teampass_db:
#create database teampass_db character set utf8 collate utf8_general_ci;

Adicionar todos os privilégios: (Neste utilizei user teampass e senha TeAmPaSs como no exemplo do site)
#grant all privileges on teampass_db.* to teampass@localhost identified by 'TeAmPaSs'; (Server (T34mp45S)

Adicionar grant para o ip do localhost também:
#grant all privileges on teampass_db.* to teampass@'192.168.206.128' identified by 'TeAmPaSs';

Aplicar privilégios:
#flush privileges;

Feito isso, instalar dependências:
#apt-get install unzip php5-common php5-mcrypt php5-mysqlnd php5-ldap -y

Criar e acessar o diretório /downloads
#mkdir /downloads
#cd /downloads

Baixar o pacote do TeamPass
#wget https://github.com/nilsteampassnet/TeamPass/archive/master.zip

Descompactar o arquivo master.zip utilizando o unzip
#unzip master.zip

Mover o arquivo descompactado (TeamPass-master) para /var/www/html/teampass (altera nome para teampass)
#mv TeamPass-master /var/www/html/teampass

Alterar o dono do arquivo: (Verificar qual o user e group do seu ambiente)
#chown -R www-data:www-data teampass

Acessar via browser para continuar a instalação:
http://{sua_url_ou_ip}/teampass/install/install.php
```
