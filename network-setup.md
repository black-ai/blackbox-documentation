## Network requirements
Blackbox units are 'plug and play' with the correct networking setup. The following are required:
* An always on, high speed internet connection
* Local ethernet network that does not require a whitelist
* Port 1194 open to allow OpenVPN connections

An always on internet connection is essential for your blackbox units. They communicate with our centralised cloud infrastructure to stitch and save your data for easy access.

_note: the system can be run locally with some modification though this feature isn't officially supported. Contact the Black.ai team if you need run your application offline._

## Unit setup
Each Blackbox unit can currently handle the inference of a single 3D sensor. Kinect v2 hardware is supported out-of-the-box, and support for ZED stereoscopic cameras and a variety of LIDAR sensors (the Blackbox operates on point-cloud data) is coming soon. Please contact the Black.ai team if you wish to use a sensor other than the kinect. 

An origin point in the observation space will need to be defined. Your blackbox units will need to be positioned around the observation space relative to this point. 

The proper positioning of Sensors attached to a Blackbox is an important step in system setup. The following should be kept in mind:

- Sensor height
- Sensor position (x and y meters relative the global 0,0 point; see Application Setup)
- Sensor angle (this is the tilt down from horizontal in degrees)
- World camera angle (counter clockwise rotation from the positive y axis on the world map in degrees)

The above measurements will need to be taken for each Blackbox connected sensor, as next they must be entered into the 'Application Config' page at config.black.ai.
