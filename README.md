# Healthcare Supply Chain using Blockchain

Test-server http://35.246.107.139 :red_circle: (offline)

### Overview ###

This Project is a feasibility study to explore how an healthcare supply-chain can be implemented with blockchain technology.

This project uses the hyperledger fabric blockchain together with the hyperledger composer tool. 

Here is an architecture overview: 
![architecture overview](https://github.com/basic-architecture.png)

Here is an uml diagram: 
![uml diagram](https://github.com/uml_diagram.png)


## Blockchain Sender

### Overview ###

I have provided source code to handle the sensors for the Healthcare Supply Chain using Blockchain project. 
I used the MFRC522 Sensor with multiple Raspberry Pi (Model 3B+). Each time the Sensor is triggered, a JSON object is sent to a MQTT broker. 


### Prerequisites ###

python3, git, python-pip3, python-dev, build-essential 

### Installation ###

```bash
sudo pip3 install RPi.GPIO
# also possible: python3 -m pip install RPi.GPIO
printf "device_tree_param=spi=on \ndtoverlay=spi-bcm2708\n" >>  /boot/config.txt
sudo raspi-config 
```
In the menu select "5 Interfacing Options"
Select "SPI" (probably 4th entry) 
When asked if you want to enable the SPI interface select "<Yes>"  
Exit menu with "<Finish>"

Reboot your Raspberry Pi
```
sudo reboot
```
```

#It is super important to INSTALL WITH PYTHON3
sudo python3 setup.py install 
pip3 install paho-mqtt python-etcd

```

### Run ###

```

python3 scan.py 
```
In another terminal you can run the `listener.py`. It listens to the default settings of `scan.py`(no flags needed). 
These are the presettings: 

receiver = "iot.eclipse.org" 	
port = 1883 			
max_timeout = 60
topic = "supply/sensor1"	

And then run the Skript: 
```
python3 listener.py
```

