## Instalando o HEROKU

sudo snap install heroku --classic

## Criando porjeto CLI

git init <nome_do_app>


## Logar no Heroku

heroku login


## Criar um porjeto no HEORU

heroku create < nome-unico-do-projeto >


## Instalar o Guicorn

pip install flask gunicorn

## AO inves de Flask run, usar localmente na porta 8000 default:

gunicorn "app:create_app()"

## Criar arquivo Procfile

touch Procfile

#### e dentro escreva:

web: gunicorn "app:create_app()"

## Adicione as dependencia remotamente

heroku buildpacks:add heroku/python

## dar o PUSH

git push --set-upstream heroku <branch>

#Algumas variáveis de ambiente - HEORKU

heroku config:set VARIABLE=this_is_the_value

### Para visualizar as variaveis

heroku config

# Rodando um Postgres no Heroku

heroku addons:create heroku-postgresql:hobby-dev

## Para ver as informações sobre o banco:

heroku pg:info

## Para ver as credenciais de conexão ao banco:

heroku pg:credentials:url


# Aviso!
###### Não compartilhe essas informações com ninguém, nem mesmo deixe explícitas no código ou envie em qualquer arquivo que esteja no repositório. Esses dados sempre devem ser adicionados às variáveis de ambiente.

######Para funcionar no psycopg2 é necessário alterar a url de postgres para postgresql.


# HEROKU 2 aulas

01:45 - heroku addons:create heroku-postgresql:hobby-dev
01:59 - heroku pg:info
02:05 - heroku pg:credentials:url
02:30 - SQLALCHEMY_DATABASE_URI=postgresql://seuUsuário:suaSenha@host:5432/nomeDoBanco
03:12 - heroku config:set SQLALCHEMY_DATABASE_URI=postgresql://seuUsuário:suaSenha@host:5432/nomeDoBanco
04:40 - pip freeze > requirements.txt
04:48 - git push --set-upstream heroku master






