# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/trusty64"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  config.vm.network "forwarded_port", guest: 8888, host: 8888

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  #config.vm.network "forwarded_port", guest: 8888, host: 8888, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  #config.vm.network "private_network", ip: "192.168.33.10"

  # 127.0.0.1:8888/?token=cad76cf21d0087eba200386a949d07fdac1b2a9275921edf

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  #config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder "./VM_Folder", "/home/vagrant/compartida"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
   config.vm.provision "shell", inline: <<-SHELL
      sudo apt update
      sudo apt -y install python3.5
      sudo apt -y install python3-pip
      sudo apt -y install ipython ipython-notebook
      sudo pip3 install --upgrade pip
      sudo pip3 install jupyter --ignore-installed six
      sudo apt -y install python3-matplotlib python3-numpy python3-scipy python3-pandas
      sudo apt -y install default-jre
      sudo apt -y install scala
      sudo pip3 install py4j
      sudo pip3 install findspark
      cd ~
      wget http://www-eu.apache.org/dist/spark/spark-2.3.2/spark-2.3.2-bin-hadoop2.7.tgz
      sudo tar -zxvf spark-2.3.2-bin-hadoop2.7.tgz
      PATH="$HOME/bin:$HOME/.local/bin:$PATH"
      export SPARK_HOME='~/spark-2.3.2-bin-hadoop2.7'
      export PATH=$SPARK_HOME:$PATH
      export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
      export PYSPARK_DRIVER_PYTHON="jupyter"
      export PYSPARK_DRIVER_PYTHON_OPTS="notebook"
      export PYSPARK_PYTHON=python3
      sudo chmod 777 ~/spark-2.3.2-bin-hadoop2.7
      sudo chmod 777 ~/spark-2.3.2-bin-hadoop2.7/python
      sudo chmod 777 ~/spark-2.3.2-bin-hadoop2.7/python/pyspark
   SHELL
end

### Up Jupyter Notebook ### 

# jupyter notebook --ip=0.0.0.0

# Access
# 127.0.0.1:8888/?token=cad76cf21d0087eba200386a949d07fdac1b2a9275921edf


##### Code for jupyter notebook ####

# import findspark
# findspark.init('/home/vagrant/spark-2.3.2-bin-hadoop2.7')
# import pyspark

###

      