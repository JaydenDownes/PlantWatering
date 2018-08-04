# PlantWatering
A small Python script to water a plant using a Raspberry Pi and Web Server!
####Instructions
#####GPIO Script
Let's start with the code for controlling the GPIO. This requires the RPi.GPIO python library which can be installed on your Raspberry Pi as follows:

`$> python3.4 -m pip install RPi.GPIO`

With that installed, you should be able to use the water.py script. You can test this is working correctly by running an interactive python session as follows:

`$> python3.4 >>> import water >>> water.get_status() >>> water.pump_on()` This should print a statement about whether your sensor is wet or dry (get_status()), and also turn on the pump for 1s. If these work as expected, you're in good shape.

At this point you can also calibrate your water sensor. If your plant status is incorrect, try turning the small screw (potentiometer) on the sensor while it is in moist soil until the 2nd light comes on.

Flask Webserver
The next aspect of this project is to setup the web server. This code can be found here in a file called web_plants.py. This python script runs a web server enabling various actions from the script described above.

You will need to keep web_plants.py in the same directory as water.py and auto_water.py described above. You will also need a subdirectory called "templates" containing the html file here called main.html.

You will need to install flask, and psutil as follows:

`$> python3.4 -m pip install flask $> python3.4 -m pip install psutil`

Make sure to place the web_plants.py file in the same directory as the water.py script above. You will also need to create a sub-directory called templates, and place main.html in the templates directory. Now run the following command command to start your web server:

`$> sudo python3.4 web_plants.py Now if you navigate to the ip address of your RPi, you should see a web dashboard`