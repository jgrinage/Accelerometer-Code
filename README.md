Connect BBB to Internet Over USB


1.  View Network Connections

2.  Select WiFi Network that you want to share internet from,right click to access properties, navigate to Sharing Tab, deselect the sharing box

3.  Click OK, then re-select WiFi Network, properties, sharing tab, select sharing box , specify BBB ethernet connection, then click OK and exit

4.  Click on ethernet for BBB, double click IPV4, select “obtain DNS automatically” and “obtain IP automatically”



Run Accelerometer Code On BBB


1. Open PuTTy

   a.  Login as root

   b.  Type: /sbin/route add default gw 192.168.7.1
   
   c.  Type: ping 8.8.8.8  // should properly ping, if not, troubleshoot before moving on
   
   d.  Type: git clone https://github.com/jgrinage/Accelerometer-Code.git
   
   e.  Navigate to directory with accel.js file
   
   f.  Type: node sensortagAccelerometer.js
   
   
2.  Make sure sensortag is on, then click the side button to connect it to the BBB


3.  Data is now being sent to the sever



Note: make sure sensortag works by double checking that your SensorTag phone app can see it.

If you get stuck, try making sure that the bluetooth adapter is turned on by running hciconfig to see if it’s “down” or “up running pscan”. If down, run in PuTTy “sudo hciconfig hci0 up”

If sensortag is acting up and not connecting in step 2, hold both side buttons for 6 seconds, let go, you will hear a noise indicating that it has been reset to default settings; this generally solves my problems

