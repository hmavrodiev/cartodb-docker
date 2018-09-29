# cartodb-docker
UBUNTU 16.04 x64

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install -y docker-ce



sudo docker pull sverhoeven/cartodb
docker run -d -p 80:80 -h <servers-external-ip-address> sverhoeven/cartodb
docker run -d -p 80:80 -h 35.185.8.28 sverhoeven/cartodb
