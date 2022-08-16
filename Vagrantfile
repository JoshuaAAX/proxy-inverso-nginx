#fuentes
#https://www.vagrantup.com/docs/provisioning/shell
#https://www.redeszone.net/tutoriales/servidores/vagrant-instalacion-configuracion-ejemplos/
#Integrantes:
#Joshua Sebastian Chicame Muñoz-2074121
#Damian Alessandro Espinosa Espinosa - 
#Adolfo Leon Maya Garcia -

Vagrant.configure("2") do |config|

       #crea la máquina virtual con nginx
        config.vm.define "nginx" do |nginx|
		nginx.vm.box = "hashicorp/bionic64"
		nginx.vm.network "private_network", ip: "192.168.28.30"
                nginx.vm.provision "shell", inline: <<-SHELL

                sudo apt-get update
                sudo apt-get install nginx -y
                sudo systemctl status ngix
                echo "hola" > hola.txt
                SHELL
       end

       #crea la máquina virtual con apache
       config.vm.define "apache" do |apache|
		apache.vm.box = "hashicorp/bionic64"
		apache.vm.network "private_network", ip: "192.168.28.32"
                apache.vm.provision "shell", inline: <<-SHELL

                sudo apt-get update
                sudo apt-get install apache2 -y
                SHELL
	end

        #crea la máquina virtual con docker-compose
	config.vm.define "compose" do |compose|
		compose.vm.box = "hashicorp/bionic64"
		compose.vm.network "private_network", ip: "192.168.28.31"
                compose.vm.provision "shell", inline: <<-SHELL

                sudo apt-get update
                sudo apt-get install nano -y
                sudo apt-get install docker-compose -y
                export CLOUDSDK_PYTHON=/usr/bin/python2
                mkdir example 
                cd example
                wget --no-check-certificate "https://docs.google.com/uc?export=download&id=1EH1zS1wQ_5WmvUEar2eXcB4QMj1Mo49g" -O docker-compose-example.tgz
                tar xfz docker-compose-example.tgz
                sudo docker-compose up             
                SHELL
	end

        
end

	
