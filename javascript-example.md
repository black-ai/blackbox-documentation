# Code Example: Javascript web dashboard #
version 0.0.1

### What is this this example application for? ###

This repository includes client side software for connecting a website to your blackbox websocket endpoint; subscribing to live data as it's generated and querying historical data.


### How do I get set up? ###

    git clone https://bitbucket.org/blackai/blackbox-dashboard-example.git

This code example is designed to run in your browser without any backend, using only Javascript on the front-end.

##### Configuration:
In black_report_client.py set the websocket address to the remote ip of your blackbox websocket endpoint
    eg: 
    
    WEBSOCKETADDR = "ws://13.x.x.xx:55955"
		
##### Dependencies:
*	scipy
*   skimage
*   websocket
	
##### How to run tests:
*	To calibrate the roomba’s wheel discrepancy so that it drives as straight run $ python drive_test.py. This will attempt to drive the roomba straight for 1.5 meters. In robot.py, modify DEFAULT_WHEEL(LR) to change the default wheel speeds of both the left and right wheels, to compensate for any unintended turning that have occurred. Once you have the roomba driving as straight as possible, measure the distance it moved. If it is not 2 meters, adjust TIME_FAC, also in robot.py, increasing if it was less than 2 meters and decreasing if it was more than 2 meters.


##### Deployment instructions:
* 	Once the roomba has been calibrated and websocket server is running run $ python black_report_client.py and the roomba will follow 
    the first track it is given by the server. 

### Contributing guidelines ###

* Writing tests:
    TBA
* Code review:
    TBA
* Other guidelines:
    TBA


### It's broken! Who do I talk to? ###
Please contact Tom Miles at tom@black.ai if you require assistance.
