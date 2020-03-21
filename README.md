Raspi-sump is a sump pit water level monitoring system using a Raspberry Pi and an 
Ultrasonic Sensor (HC-SR04)


![alt tag](http://www.linuxnorth.org/raspi-sump/images/raspi-chart.png)


Currently the system monitors the water level in your pit at defined intervals. It sends
email sms alerts if the water reaches a critical level, indicating a possible sump pump failure.

# Discord Group 30 day trial

21-03-2020  - We are currently doing a 30 day trial on Discord for Raspi-Sump users. If you are interested send me an email (alaudet@linuxnorth.org) and I will send you an invite link.

Discuss and get support from other users.


# Installing with pip version 9 or greater


Pip versions > 7 default to Wheels which omits some folder setup in setup.py.
If using Raspbian Stretch or later versions install as follows;

    sudo pip3 install --no-binary :all: raspisump



# New in Version 1.2 

Added improvements to SMS/Email Alerts

1 - Alerts now contain hostname to better identify which instance of Raspi-Sump is
reporting.

2 - Heartbeat SMS/Email notifications can be enabled to send at a user defined interval, to let you know
that alerts are working.  


Added to [Email] section of raspisump.conf

    heartbeat = 0 or 1 (disabled or enabled)
    heartbeat_interval = user defined number of minutes between notifications

If configuration items are not present in raspisump.conf the default is set to
off (no notifications)


For more information see [Issue 7](https://github.com/alaudet/raspi-sump/issues/7).

# QUICK INSTALL 


Install the pip package manager (if not present on your pi).

    sudo apt-get install python3-pip


Install Raspi-Sump.

    sudo pip3 install --no-binary :all: raspisump

Upgrading an existing version


    sudo pip3 install -U raspisump

This will also install the [HCSR04sensor](https://github.com/alaudet/hcsr04sensor) and  RPi.GPIO modules if not present on your Pi.

If you want to use charts install maplotlib.

    sudo apt-get install python3-matplotlib


Matplotlib should install Numpy.  If you need to install Numpy seperately;

    sudo apt-get install python3-numpy

Read the configuration docs copied during setup on your pi at the following location;

    /home/pi/raspi-sump/docs

They are also available on github https://github.com/alaudet/raspi-sump/blob/master/docs/install.md


# Upgrading from Python2 to Python3 (Raspbian Jessie)

    sudo pip uninstall raspisump
    sudo pip3 install raspisump


Your configuration file will be preserved in /home/pi/raspi-sump/


# Python2 install (End of Life is January 1, 2020)

Python2 installs of Raspi-Sump are no longer be supported.


# More Info

Further details provided at http://www.linuxnorth.org/raspi-sump/

An example hourly updating graph is available for view.
http://www.linuxnorth.org/raspi-sump/raspi-sump-today.html

# Disclaimer

You are welcome to use Raspi-Sump but there is no guarantee it will work. Your house may still flood if your sump pump fails. This software comes with no warranty. See License details.

This is not a replacement for remaining vigilant in maintaining your water pumping system. It is one tool you can use to give yourself extra piece-of-mind.

Best practices should also include:

* A backup pump that triggers at a slightly higher water level than your main pump.
* The secondary pump should be connected to a seperate dedicated electrical breaker. 
* You should also have a generator that can provide power should you have an extended outage during the spring or other unseasonally wet time of year.
* if you are building a new home, pay attention to the grade of your property, as you may even be able to let gravity empty your pit for you.  That would be the best approach with a backup pump just in case. 

Once you have done all of these things, then consider using a monitoring system like Raspi-Sump.

# License

MIT License.  I want you to do whatever you want with Raspi-Sump.  If you
improve it please let me know.

# Contributing

Please refer to CONTRIBUTING.md in the root of the repository for contribution guidelines.

# Donate

[Your Donation is Appreciated](https://www.linuxnorth.org/donate/)
