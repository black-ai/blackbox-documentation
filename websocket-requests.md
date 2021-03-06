## Making Websocket Requests
The Blackbox websocket API structure is quite straightforward. Following are the components of making websocket requests.  

#### Authentication
You will be provided with API credentials by either direct contact from black.ai or through the Application Config page. 

_Note: Please contact us if your Application does not show automatically generated API credentials._
 
#### API Architecture
The Blackbox API follows a simple 'publisher / subscriber' model, making it possible to query for data both historically and in real-time.  

The topics you can subscribe to currently include: 

- Persons tracked (tracks)
- Walkable surfaces (floormap)

All publishers and subscribers have subscription types which let you handle the messages received by your client-side application accordingly.

The basic request format is: 

{requestType: <type>, topicInfo: <topic>, data: <additional_params>}

where requestType, topicInfo, and data will vary depending on what information you are wanting to pull from the  API. 


requestTypes in general are constants
Publishers

#### NewTrack:
This sends out the latest tracks in the system which the client was earlier not notified about. 

This sends out the latest tracks in the system which the client was not earlier notified about. 
If the client closes and reopens the connection, this process will start again. The format of the information would be:


        {"data": "<trackid1>", "subscriptiontype": "newtrack"}
    
parameters:

        data : trackids of the track    type: GUID
        subscriptionType : type of subscription 


#### ExpiredTrack:
This sends out the expired tracks in the system which the client was earlier notified about. 
If the client closes and reopens the connection, this process will start again. The format of the information would be:
The format of the information would be:

        {"data": "<trackid1>", "subscriptiontype": "expiredtrack"}
    
parameters:

        data : trackids of the track    type: GUID
        subscriptionType : type of subscription 


#### FloorMap
This sends out the floormap of the global space that the blackbox operates in. The client is automatically subscribed to the floormap on connection, and automatically unsubscribed once the floormap is published. The client can subscribe to the floormap specifically at any point in time (please refer to the subscription section for more information).

The floor map has a default 10x10 cm cell size (see Application Config => Mapping Granularity).
    
Format:

        {"subscriptionType": "floormap", data : <floormap>, "extradata": {
                            "xmin": xmin , "ymin" : ymin , "xmax" : xmax , "ymax" : ymax , "xdim" : xdim , "ydim" : ydim}}
    
parameters:

        data : floormap    type list[list[]] basically a 2d array
        extradata : has extra information about the floormap
        xmin,ymin,xmax,ymax : the actual minimum and maximum points of the floor             type: float    
            example: -4.098,-5.098,4.098,5.098
        xdim,ydim : dimension of the floormap given                                          type : int     example: 50,60
        

#### Track

This sends out the positions of tracks subscribed by client (handled in subscription section)
The track positions are oriented to the floormap indices
    
Format:
    

	{"data": { {
                        "track_id": <trackid1>,
                        "position": {"x": trackid1.position.x, "y": trackid1.position.y}, // type : int 
                        "velocity": {"x": trackid1.velocity.x, "y": trackid1.velocity.y}, // type : float
                        "timestamp": data.header.stamp.nsecs
               },
               {
                        "track_id": <trackid2>,
                        "position": {"x": trackid2.position.x, "y": trackid2.position.y}, // type : int 
                        "velocity": {"x": trackid2.velocity.x, "y": trackid2.velocity.y}, // type : float
                        "timestamp": data.header.stamp.nsecs
               }   
               }, "subscriptionType": "track"}
   
parameters:
        
	position: x,y positions of the track x,y are both ints relative to the floormap
        velocity : x,y velocities in floats 
        timestamp : time in timestamp
        

## Subscriptions

    This is the list of subscriptions . The subscriptions generally have message types attached to them. 
    The messagetypes are either subscribe  or unsubscribe,

FloorMap
    The client could either subscribe or unsubscribe to the floormap. 
    Please note that the client is auto subscribed to the floormap on connection and 
    auto unsubscribed once the floormap is published.
    However, the client could fetch the floormap whenever it wants.
    
    Format:
     subscribe:   {"messageType": "subscribe", "subscriptionType": "floormap", labels.data: None}
     unsubscribe: {"messageType": "unsubscribe", "subscriptionType": "floormap", labels.data: None}
     
Track
    The Tracks being published earlier are those which are subscribed by the client. 
    This is how you subscribe or unsubscribe to the tracks
    
    Format:
        subscribe   :  {"messageType": "subscribe", "subscriptionType": "track", labels.data: {"trackid1","trackid2"}}
        unsubscribe :  {"messageType": "unsubscribe", "subscriptionType": "track", labels.data: {"trackid1","trackid2"}}

#### TrackHistory
    
This sends the list of tracks that the system has seen in the last amount of time specified in hours
    
Request format:

        {"messageType" : "subscribe", "subscriptionType": subscriptionType, "durationinhours": durationinhours}
        
Response Format:

        {"data" : {"track1" : <trackid1> , "track2" : <trackid2>}, "subscriptionType" : "trackhistory"}
    
request parameters:

        durationinhours : period of time you want it from  example : 1 , meaning the last 1 hour


[back](./)
