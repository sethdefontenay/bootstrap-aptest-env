Vagrant.configure("2") do |config|
  config.vm.box = "peru/ubuntu-18.10-desktop-amd64"
  config.vm.box_version = "20190101.01"
  config.vm.provision "shell", inline: <<-SHELL
	 sudo apt-get update
     sudo apt-get install -y python3.7 python3-pip git virtualenv curl
	 snap install postman
	 snap install pycharm-community --classic
	 sudo snap install docker
	 sudo groupadd docker
	 sudo usermod -a -G docker vagrant
	 sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
	 sudo chmod +x /usr/local/bin/docker-compose
	 git clone https://github.com/sethdefontenay/apbackendtest.git
	 sudo chown -R vagrant:vagrant /home/vagrant/apbackendtest
	 cd apbackendtest
	 ./setup.sh
	 docker pull mongo
	 docker pull sethdefontenay/reliabilly:latest
   SHELL
end
