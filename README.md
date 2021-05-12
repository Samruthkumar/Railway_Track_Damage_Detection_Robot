# Railway_Track_Damage_Detection_Robot
Our Robot(Four wheeler) detects damages on railway track and sends their coordinates to database and later the remote station coordinator 
will log in into their respective station account and can see the damaged coordinates and rectify damages.

The 4 wheeler robot has an Arduino broad, a Raspberry pi, servo motor, pi camera and ultra sonic sensors on it.

We have a Arduino Uno board on our robot and we attach a Ultrasonic sensor, servo motor to the board. Ultrasonic sensor claculates the distance between itself
and railway track. Because railway tracks are parallel there won't be change in diastance between ultrasonic sensor and railway tracks. If there is a change
in distance then Arduino uno board consider it as a damage and sends signal to raspberry pi for coordinates of the location. To identify intensional gaps and do not
let our robot to detect them as damage, we keep a if loop such that if the gap between the ultrasonic sensor and railway track is equal to intensional gap then our
robot do not consider it as damage. Otherwise it detects them as a damage. After detecting damages by Arduino uno board, it will send signal to raspberry pi for damaged coordinates.
Raspberry pi then sent a request to the server that we defined. The server sends coordinates to pi. After that pi takes photos of damaged place in three angles 0, 90, 180.
This can be done using servo motor as it is attached to pi camera, the camera can be rotated by the angles 0,90,180 by the servo motor.

  After that raspberry pi sends coordinates and images to the server database. This sever different from the server that is used to get damaged coordinates. Finally when respective station cordinator log in to their account the damaged cordinates will be displayed on his device.
  
  
  The server code for getting coordinates is in LocationAPI.zip
  
  The server or web application code for storing coordinates of damaged place and to display those coordinates when requested is in Web_app.zip
  
  The code for detecting damages using Aurduino uno board is in Aurdino-Uno code.txt file
