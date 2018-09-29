# cartodb-docker
UBUNTU 16.04 x64

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install -y docker-ce



sudo docker pull sverhoeven/cartodb
sudo docker run -d -p 80:80 -h <servers-external-ip-address> sverhoeven/cartodb
sudo docker run -d -p 80:80 -h 35.227.102.157 sverhoeven/cartodb


sudo docker create --name cartodb_pgdata sverhoeven/cartodb
# Change to directory to save the Postgresql data dir (cartodb_pgdata) of the CartoDB image
sudo docker cp cartodb_pgdata:/var/lib/postgresql $PWD/cartodb_pgdata
sudo docker rm -f cartodb_pgdata

sudo docker run -d -p 80:80 -h cartodb.example.com -v $PWD/cartodb_pgdata:/var/lib/postgresql sverhoeven/cartodb

dev - >pass1234
