sudo apt update && sudo apt upgrade

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

sudo apt update

sudo apt -y install postgresql

#ACESSANDO POSTGRESQL
sudo -u postgres psql

#CRIANDO NOVO USUARIO
postgres=# CREATE USER <meu_usuario> SUPERUSER CREATEROLE CREATEDB PASSWORD '1234';

#CRIANDO UM BANCO
CREATE DATABASE <meu_usuario>;

#ADICIONANDO UM USUARIO na linha de comando do PostgreSQL

CREATE USER <seu_usuario> SUPERUSER CREATEROLE CREATEDB PASSWORD <sua_senha>;
 
CREATE DATABASE nome_do_seu_usuario;


AGORA PODE USAR O COMANDO psql no terminal para abrir.
