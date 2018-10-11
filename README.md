# VAGRANT DEVELOPMENT FOR SPARK WITH JUPYTER NOTEBOOK

Virtual machine for development. Jupyter Notebook configurated and shared folder for file pass between local host y virtual machine enviroment. 

## Steps:
--
	- Clone this repository
	- In the principal folder run `vagrant up` and wait for finish process.
	- Run `vagrant ssh` command for login in VM
	- Run `jupyter notebook`, copy the url access in browser application
	- In case of any error: In the `Vagranfile` you will see the command secuence for apply all necesary configuration


## The config command secuence, in linux enviroment, is:
-----------------------------------

- `sudo apt update`
- `sudo apt -y install python3.5`
- `sudo apt -y install python3-pip`
- `sudo apt -y install ipython ipython-notebook`
- `sudo pip3 install --upgrade pip`
- `sudo pip3 install jupyter --ignore-installed six`
- `sudo apt -y install python3-matplotlib python3-numpy python3-scipy python3-pandas`
- `sudo apt -y install default-jre`
- `sudo apt -y install scala`
- `sudo pip3 install py4j`
- `sudo pip3 install findspark`
- `cd /home/vagrant`
- `wget http://www-eu.apache.org/dist/spark/spark-2.3.2/spark-2.3.2-bin-hadoop2.7.tgz`
- `sudo tar -zxvf spark-2.3.2-bin-hadoop2.7.tgz`
- `PATH="$HOME/bin:$HOME/.local/bin:$PATH"`
- `export SPARK_HOME='/home/vagrant/spark-2.3.2-bin-hadoop2.7'`
- `export PATH=$SPARK_HOME:$PATH`
- `export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH`
- `export PYSPARK_DRIVER_PYTHON="jupyter"`
- `export PYSPARK_DRIVER_PYTHON_OPTS="notebook"`
- `export PYSPARK_PYTHON=python3`
- `sudo chmod 777 /home/vagrant/spark-2.3.2-bin-hadoop2.7`
- `sudo chmod 777 /home/vagrant/spark-2.3.2-bin-hadoop2.7/python`
- `sudo chmod 777 /home/vagrant/spark-2.3.2-bin-hadoop2.7/python/pyspark`