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
*	To calibrate the roomba's wheel discrepancy so that it drives as straight as possible, run $ python drive_test.py
    This will attempt to drive the roomba straight for 1.5 metres. In robot.py modify DEFAULT_WHEEL(L/R) to change the 
    defult wheel speeds of the left and right wheels to compensate for any unintended turning that may have occured.
    Once you have it driving as straight as possible, measure the distance it moved, if it is not 2 meters, adjust TIME_FAC
    also in robot.py, increasing if it fell short or decreasing if it overshot.

##### Deployment instructions:
* 	Once the roomba has been calibrated and websocket server is running run $ python black_report_client.py and the roomba will follow 
    the first track it is given by the server. 

### Contributing guidelines ###

* Writing tests:
    tba.
* Code review:
    tba.
* Other guidelines:
    tba.


### It broke. Who do I talk to? ###
* Tom Miles: tom@black.ai