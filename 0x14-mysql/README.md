# 0x14-mysql

## how to install MySQL 5.7.x (5.7.42)
download DEB Bundle from :
https://downloads.mysql.com/archives/get/p/23/file/mysql-server_5.7.42-1ubuntu18.04_amd64.deb-bundle.tar

Extracting files from Archive :
tar xvf mysql-server_5.7.42-1ubuntu18.04_amd64.deb-bundle.tar

install mysql :
sudo dpkg -i *.deb

install dependencies :
sudo apt-get -f install

check :
mysql --version

