## Account setup
Account registration is currently limited to a small number of early partners and will be open to the public soon. If you are a member of a research institution across Asia Pacific or North America and are interested in beta testing or piloting the system please contact us at [contact@black.ai](mailto:contact@black.ai)

Account setup and configuration involves 3 steps: 
1. Unit Registration

    Once logged in to your account at [config.black.ai](http://config.black.ai), visit the [Account page](http://config.black.ai/account) to view any Blackbox units linked to your user account.
    
    If you have any Blackbox units on hand that are yet to be added to the system, simply enter the unit's hardware ID, registration key, and a nickname by which this unit can be easily identified. We recommend labelling the underside of your units so they can be physically idenfied during the config phase.
    
    **Warning: once registered units cannot currently be renamed.**
     
    If your newly registered units don't appear after form submission, reload the page. 
    
    _Note: your Black.ai contact may have already completed this step for you._

2. Application Creation:
    
    Next, visit the [Application page](http://config.black.ai/applications) to view autonomous applications linked to your account. 
    
    Simply click configure on an existing application or create a new one. Applications _can_ be renamed once set.

    If your new application doesn't appear after form submission, reload the page and proceed to configure.

3. Application Config:
    
    The Application Config page is where you set up and fine-tune an individual application. Application configuration can be largely divided into two parts:
    
    1. core application config; and
    2. unit / sensor positioning.
    
    ###### Step 1: Core Application Config
    
    On the left of this page you will see a graph (top-down map) representing your Application Space. This is a visual guide to the physical domain in which your autonomous system will operate, and is a bounding area that encapsulates the sensors and Blackbox units you will be positioning.
     
    On the right side of the page is the "Core Application Configuration" dialogue with a few parameters to tweak:
    
    * Application Name
        * A nickname for this application.
    * Application Width 
        * The width of the global coordinate space **in meters**.
    * Application Height
        * The height of the global coordinate space **in meters**.
    * Coordinate Generation
        * **Note: temporarily disabled.** This defines the method by which your application graph is generated. In a static system, you manually define the x,y bounds of the global coordinate space. In a dynamic system, we automatically learn the global x,y coordinate minuma and maxima, growing out the global coordinate space over time.
    * Mapping Granularity
        * **Note: temporarily disabled.** This is the positional accuracy of static object location on the graph API in milimeters. We suggest a value of 30 for best performance. 
        
    ###### Step 2: Unit / Sensor Config
    
    Above the Core Application Config dialogue is a button to switch to the Unit Config tag. Press this. 
    
    If you do not yet have any units linked to this application, they should appear at the bottom with a button to 'link', just press this. 
    
    Once units are linked, you should see an edit button to position them in the world space. If this doesn't appear, reload the page. 
    
    Within the unit edit dialogue, there are four parameters to configure:
    
    * Sensor x position
        * The x coordinate of this sensor (attached to the Blackbox unit) **in meters** relative to the global (0,0) root. 
    * Sensor y position
        * The y coordinate of this sensor (attached to the Blackbox unit) **in meters** relative to the global (0,0) root.     
    * Sensor pitch
        * The angle in degrees between the horizontal axis and the forward face (longitudinal axis) of your sensor.
    * Sensor yaw
        * The angle in degrees counter-clockwise from the positive Y axis of your global Application space. 
    
    An example unit config:
    
        x position      : 5.3
        y position      : 10
        pitch           : 20
        yaw             : 180

    *Note: if you do not see any units on this dialogue, linked or otherwise, first make sure you have registered units to your account then ensure they aren't linked to another application.*