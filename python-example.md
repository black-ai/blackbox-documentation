# Code Example: Python #
version 0.0.1

### What is this this example application for? ###

This repository includes client side software for controlling a roomba robot with assistance from a blackbox websocket endpoint to navigate through a space and follow a target person track.

### How do I get set up? ###

    git clone https://bitbucket.org/tgsmiles/roomba-bot.git

This code is designed to be run on a raspberry pi 3 connected to a roomba via USB to the serial port on the roomba.

##### Configuration:
In black_report_client.py set the websocket address to the remote ip of your blackbox websocket endpoint
    eg: 
    
    WEBSOCKETADDR = "ws://13.x.x.xx:55955"
		
##### Dependencies:
*	scipy
*   skimage
*   websocket
	
##### How to run tests:
To calibrate the roomba's wheel discrepancy so that it drives as straight as possible, run $ python drive_test.py
    This will attempt to drive the roomba straight for 1.5 metres. In robot.py modify DEFAULT_WHEEL(L/R) to change the 
    defult wheel speeds of the left and right wheels to compensate for any unintended turning that may have occured.
    Once you have it driving as straight as possible, measure the distance it moved, if it is not 2 meters, adjust TIME_FAC
    also in robot.py, increasing if it fell short or decreasing if it overshot.

##### Deployment instructions:
Once the roomba has been calibrated and websocket server is running run $ python black_report_client.py and the roomba will follow 
    the first track it is given by the server. 

### Contributor guidelines ###

* Writing tests:
    tba.
* Code review:
    tba.
* Other guidelines:
    tba.


### It broke. Who do I talk to? ###
* Tom Miles: tom@black.ai