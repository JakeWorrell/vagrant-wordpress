Vagrant::Config.run do |config|
	# Every Vagrant virtual environment requires a box to build off of.
	config.vm.box = "lucid32"

	# Forward port 8080 on the host to port 80 on the VM
	config.vm.forward_port "http", 80, 8080

	# Map project source folder to VM
	config.vm.share_folder("wordpress", "/var/www/wordpress/wp-content/themes/ellywilloughby.co.uk", "../wordpress/")

	# Provision with chef solo
	config.vm.provision :chef_solo do | chef |
		chef.cookbooks_path = "cookbooks"
		chef.add_recipe("jake_wordpress")
	end
end
