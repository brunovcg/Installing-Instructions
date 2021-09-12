sudo apt update && sudo apt upgrade

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

sudo apt update

sudo apt -y install postgresql

#ACESSANDO POSTGRESQL
sudo -u postgres psql

#CRIANDO NOVO USUARIO
postgres=# CREATE USER <USUARIO> SUPERUSER CREATEROLE CREATEDB PASSWORD '1234';

#CRIANDO UM BANCO
CREATE DATABASE <USUARIO>;
