.PHONY: install compose stop remove
install:#build images
	docker build -t target:latest . -f=machines/targetfile
	chmod 755 ./machines/start.sh
	docker build -t attack . -f=machines/attackfile
	docker-compose -f ./machines/docker-compose.yml up -d
stop:#stop the containers
	docker-compose -f ./machines/docker-compose.yml stop
remove:#remove the containers
	docker-compose -f ./machines/docker-compose.yml down
