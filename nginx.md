# No terminal

sudo apt install nginx


sudo service nginx start


sudo code /etc/nginx/sites-enabled/default



# Declarando um servidor, substituir o que já tem

	
	server {

	    # Esse servidor escuta na porta 80 da nossa maquina
	  listen 80 default_server;
	  listen [::]:80 default_server;

	    # Um nome qualquer para o servidor, em producao se tiver um dominio example.com 	vai usar aqui

	  server_name _;

	    # Aqui vamos criar rotas para esse servidor escutando na porta  HTTP 80
	  location / {

	  }

	}


# Declarando um servidor com as locations

server {

    # Esse servidor escuta na porta 80 da nossa maquina
  listen 80 default_server;
  listen [::]:80 default_server;

    # Um nome qualquer para o servidor, em producao se tiver um dominio example.com vai usar aqui
  server_name _;

    # Aqui vamos criar rotas para esse servidor escutando na porta  HTTP 80

    # Vamos utilizar a raiz "/" seguido do nome do nosso servico para ficar bem claro o funcionamento
  location /app1 {
		# Utilize 0.0.0.0 ao inves de 127.0.0.1 ou localhost, evita problemas.
		# Utilize ; ao final, sintaxe parecida com JS.
		proxy_pass http://0.0.0.0:5001/;
	  }

	  location /app2 {
		proxy_pass http://0.0.0.0:5002/;
	  }

	    # Aqui pode criar quantos mais quiser nesse mesmo padrao para testar
          }

# Atualizar o nginx

sudo service nginx restart

# Adicionando Load Balancer

sudo code /etc/nginx/sites-enabled/default

	# responde na raiz ou seja http://localhost/
	location / {
		proxy_pass http://backend;
	}
	
# Editando as configs

sudo code /etc/nginx/nginx.conf

### Na seção HTTP crie um bloco iniciado por upstream como abaixo preferência no final dessa seção, antes de fechar o }:

	upstream backend {
		# Adicionando a aplicacao da porta 5001 ao nosso grupo backend
		server 0.0.0.0:5001 weight=1;
		# adicionando a aplicacap da porta 5002 ao nosso grupo porem com peso 2
		server 0.0.0.0:5002 weight=2;

	    # Aqui voce poderia continuar adicionando outros servicos para responderem nesse balancer
	}












