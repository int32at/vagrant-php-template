$name = "vagrant-php-template"

$script = <<SCRIPT
echo starting installation
apt-get update -y
sudo apt-get install -y apache2 libapache2-mod-php5 php5
sudo rm -rf /var/www/html
sudo ln -s /vagrant/src /var/www/html
echo "ServerName localhost" >> /etc/apache2/apache2.conf
echo "<Directory /var/www/>
	Options Indexes FollowSymLinks
	AllowOverride All
	Require all granted
</Directory>" >> /etc/apache2/apache2.conf
sudo a2enmod rewrite
sudo a2enmod headers
sudo service apache2 restart
echo installation done
SCRIPT

Vagrant.configure(2) do |config|
	config.vm.box = "ubuntu/trusty64"
	config.vm.hostname = "vagrant"
	config.vm.network "forwarded_port", guest: 80, host: 8080
	config.vm.synced_folder ".", "/vagrant", owner: "vagrant", mount_options: ["dmode=775,fmode=775"]
	config.vm.provider "virtualbox" do |vb|
		vb.name = $name
 		vb.memory = 256
	end
	config.vm.define $name do |t|
  	end
	config.vm.provision "shell", inline: $script
end
