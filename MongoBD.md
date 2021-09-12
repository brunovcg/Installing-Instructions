wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -

echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list

sudo apt update

sudo apt install -y mongodb-org

echo "mongodb-org hold" | sudo dpkg --set-selections

echo "mongodb-org-database hold" | sudo dpkg --set-selections

echo "mongodb-org-server hold" | sudo dpkg --set-selections

echo "mongodb-org-shell hold" | sudo dpkg --set-selections

echo "mongodb-org-mongos hold" | sudo dpkg --set-selections

echo "mongodb-org-tools hold" | sudo dpkg --set-selections

# INICIAR O MONGO
sudo systemctl start mongod

# VERI8FICAR SE RODOU
sudo systemctl status mongod

#INICIAR JUNT COM O SISTEMA
sudo systemctl enable mongod





