# insecure_bank, pequeno website para demonstrar vulnerabilidades em aplicações Web

autor: Osvaldo Santos, Instituto Politécnico de Castelo Branco


Instruções para instalar o website numa VM com Ubuntu 22

#update dos repositórios de software

sudo apt update


#instalar os diversos softwares

sudo apt update
sudo snap install code -y
sudo apt install node -y
sudo apt install npm -y
sudo apt install mysql-server -y
sudo apt install php -y
sudo apt install apache2 -y
sudo ufw allow in "Apache"
sudo apt install git -y
sudo apt install libapache2-mod-php -y
sudo apt install php-mysql -y


#ir para o documento root do apache

cd /var/www/html


#clonar o website a partir do git-hub, para a pasta insecure dentro de /var/www/html

sudo git clone https://github.com/droneipcb/insecure_bank_php.git insecure


#ir para a pasta do website

cd /var/www/html/insecure


#abrir a consola do mysql

sudo mysql


#criar a base de dados a partir de um script

mysql> source create_database.sql

mysql> exit


#alterar as permissoes da pasta para os uploads

sudo chown -R www-data:www-data uploads


#arrancar o apache

sudo systemctl restart apache2


#e criar um shortcut no desktop

sudo ln -s /var/www/html/insecure ~/Desktop/

