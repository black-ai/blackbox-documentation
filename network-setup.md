## Network requirements
Blackbox units are 'plug and play' with the correct networking setup. The following are required:
* A high speed internet connect that is always online
* A local ethernet network that does not require a whitelist
* Port 1194 open to allow OpenVPN connections

Ensuring that the internet connection is always online is essential for the Blackbox units. They continuously communicate with our centralised cloud infrastructure to stitch and save your data for easy access at any time. 


_Note: the system can be run locally with some modification, though this feature isn't officially supported. Contact the black.ai team if you need run your application offline._

## Unit setup
Each Blackbox unit can currently handle the inference of a single 3D sensor. Kinect v2 hardware is supported out-of-the-box, and support for ZED stereoscopic cameras and a variety of LIDAR sensors (the Blackbox operates on point-cloud data) is coming soon. Please contact the black.ai team if you wish to use a sensor other than the kinect. 

An origin point in the observation space will need to be defined. Your Blackbox units will need to be positioned around the observation space relative to this point. 

The proper positioning of sensors attached to a Blackbox is an integral step in system set up. To ensure this is done correctly, the following factors should be kept in mind:

- Sensor height
- Sensor position (x and y meters relative the global 0,0 point; see Application Setup)
- Sensor angle (this is the tilt down from horizontal in degrees)
- World camera angle (counter clockwise rotation from the positive y axis on the world map in degrees)

The above measurements will need to be taken for _each_ Blackbox connected sensor, as next they must be entered into the 'Application Config' page at config.black.ai.
