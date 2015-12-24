

Vagrant.configure("2") do |config|
	# Vagrant 1.7.  tcuser works with the username docker
	# https://github.com/mitchellh/boot2docker-vagrant-box/issues/79
	config.ssh.username = 'docker'
	config.ssh.password = 'tcuser'

	#config.ssh.insert_key = false	

	# this configs docker as the provider in the box
	# this allows us to use vagrant in lieu of boot2docker
	# on windows and osx
	config.vm.provider "docker" do |d|
		# this will pickup the Dockerfile in project dir
		d.build_dir = "."
	end

	# this syncs the src folder on the host with /src
	# folder in guest VM which in turn will sync with
	# docker image, Vagrant handles this volume connection
	config.vm.synced_folder "src/", "/src/"


end