# projectfile
* sudo apt update -y
* sudo apt upgrade -y
* sudo apt-get install docker.io -y
* sudo apt install curl -y
* sudo groupadd docker
* sudo gpasswd -a $USER docker
* #如果直接用install docker-compose會產生錯誤
* sudo curl -L "https://github.com/docker/compose/releases/download/1.28.6/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
* sudo chmod +x /usr/local/bin/docker-compose
* sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
* sudo apt install make -y
* make -f ELK install
* make -f machine install
