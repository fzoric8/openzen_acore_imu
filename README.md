# openzen_acore_imu

Package for launch files that start adequate number of IMUs for specific use-case. 

In case of automatonomous separator set up on powerlines, we need 3 IMUs to determine 
powerline pose accurately. 

Packages that are needed to run this package smoothly are following: 
 * [openzenros](https://bitbucket.org/lpresearch/openzenros/src/master/) 
 * [openzen-sensor](http://wiki.ros.org/openzen_sensor) 

For the first one you can follow instructions and clone it from bitbucket repo in workspace
source and build it as required. For the openzen-sensor you can dowload it and build it with: 
```
sudo apt-get install ros-melodic-openzen-sensor
```

If you get following error: 
```
[ERROR] [1616596198.085798265]: Cannot connect directly to sensor.  Make sure you have the user rights to access serial devices.
[ERROR] [1616596198.085824606]: OpenZen sensor could not be connected
```

That means that you don't have adequate permissions for IO devices.

You can check which serial ports are available: 
```
dmesg | grep tty
```

You can change permissions with following command: 
```
sudo chmod 777 /dev/ttyUSB0
```

