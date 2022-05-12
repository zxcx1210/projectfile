.PHONY:beat
beat:
	apt update 
	apt upgrade -y
	apt install -y curl ca-certificates vim
	curl -L -O https://artifacts.elastic.co/downloads/beats/packetbeat/packetbeat-8.1.3-linux-x86_64.tar.gz
	tar xzvf packetbeat-8.1.3-linux-x86_64.tar.gz
	cd ./packetbeat-8.1.3-linux-x86_64 && \
	sed -i 's/#setup.dashboards.enabled: false/setup.dashboard.enabled: true\nsetup.template.overwrite: false/g' packetbeat.yml && \
	sed -i 's/hosts: \["localhost:9200"\]/hosts: \["elasticsearch:9200"\]/g' packetbeat.yml && \
	sed -i 's/#username: "elastic"/username: "elastic"/g' packetbeat.yml && \
	sed -i 's/#password: "changeme"/password: "M@selab"/g' packetbeat.yml && \
	sed -i 's/#host: "localhost:5601"/host: "elasticsearch:5601"\n  username: "elastic"\n  password: "M@selab"/g' packetbeat.yml && \
	./packetbeat setup -e && \
	chown root packetbeat.yml && \
	./packetbeat -e
