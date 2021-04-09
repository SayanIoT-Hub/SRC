# SRC robot (Self driving RC Car)
## Fully hand-made metal mobile robot
As [Self Driving robot Engineer] I made fully hand-made metal Self Driving RC car.
![SRC B1 side1](https://user-images.githubusercontent.com/32663016/114177094-f45f2980-9976-11eb-9b19-e24f371d349c.png)
![SRC B1 side2](https://user-images.githubusercontent.com/32663016/114177226-1bb5f680-9977-11eb-9252-aefe00bdafe6.png)

## HW Detail 
- Main Controller: Latte panda(Window or Ubuntu), Raspberry pi
- Sub Contoller: Arduino > motor, light, LED dot matrix control
- IMU (AHRS): Heading direction check
- Lidar: Emergency stop, collision avoidance
- Camera: Lane detection, Machine Learning (Object detection)
- Speaker: Connection beep, Alarm, Music(wav)
- Light: 12 LED for light / mode check, night driving test

### GNSS/GPS
- GNSS: RTK fixed or float mode setting (RTCM message) using NTRIP client
- NTRIP client: u-center, Lefebure
- Base Station: gnss.eseoul.go.kr, vrs3.ngii.go.kr
- Map: Google satellite, Bing..
![gnss gmap](https://user-images.githubusercontent.com/32663016/114179669-3dfd4380-997a-11eb-977b-56b9888c949e.png)

### IMU/ AHRS
- AHRS Heading
- Kalman Filter
![ahrs v1 -1](https://user-images.githubusercontent.com/32663016/114178669-ff1abe00-9978-11eb-8b3f-0e7afb4f1d23.png)

### LED light
- 12 Led module using relay switch module
- color: bule, white, yellow ...
![LED light-day](https://user-images.githubusercontent.com/32663016/114179881-8583cf80-997a-11eb-9ae0-7dd882dc87d3.png)
![LED light-night](https://user-images.githubusercontent.com/32663016/114179973-98969f80-997a-11eb-89ba-7d0b254e59eb.png)

### SRC Type
![SRC-BC](https://user-images.githubusercontent.com/32663016/114103638-73ffe080-9904-11eb-9f0f-82286d8f09cf.png)

### Led dot matrix
- Display info: distance gap, degree gap, time, Latitude, Longitude,...
- Mode select: joystic
![led dot matrix](https://user-images.githubusercontent.com/32663016/114180465-30948900-997b-11eb-9e82-c2dd3f397627.png)

### Joystick
- SRC Manual control
- Mode select: Manual/ Self Driving
- Etc: Sound check, LED Light on/off
![joystick](https://user-images.githubusercontent.com/32663016/114184555-d518ca00-997f-11eb-88d3-edc224391c71.png)

### Camera /vision
- image processing: Binary conver
![image lane detection](https://user-images.githubusercontent.com/32663016/114181877-047a0780-997d-11eb-8480-14f319f0261d.png)

### Speaker
- Function: connection alarm, Music, 


## SW Detail
### Steering
- Steering: pure pursuit and PID control
- PID: minimize the angle difference between waypoint and agv-lookahead point
![steering diagram](https://user-images.githubusercontent.com/32663016/114169812-03d97500-996d-11eb-831b-41ac7f2191fa.png)

### Waypoint
- GPX format: Using GPX route editor to create, modify the route easily.
- Basic: Lookahead point, Target position, Heading value > minimize degree gab(waypoint vs AGV-lookahead deg)
![waypoint detail](https://user-images.githubusercontent.com/32663016/114104917-b9bda880-9906-11eb-9364-4e94e936f8db.png)
- Tools: Using GPX route editor, easy to make and modify waypoint for driving
![gpx route editor](https://user-images.githubusercontent.com/32663016/114106540-f0e18900-9909-11eb-8efd-35cec42236dc.png)
- Coordination: WGS84 to TM transform
![coordinate transformation](https://user-images.githubusercontent.com/32663016/114106125-115d1380-9909-11eb-8894-97cdaa8b7b61.png)

### Log replay
- replay the logfile after driving.
- waypoint / actual driving route compare
- statistics: distance error max/min/average
- control value check: PID, stop point etc check..
![log analysis](https://user-images.githubusercontent.com/32663016/114105530-e2926d80-9907-11eb-81bf-85ef355ecca8.png)

### Reinforcement Learning
- Model: I'm testing DQN logic to apply driving algorism 
