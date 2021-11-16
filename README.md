# EnvironmentSensors

## Overview
Most Android-powered devices have built-in sensors that measure motion, orientation, and various environmental conditions. These sensors are capable of providing raw data with high precision and accuracy, and are useful in monitoring changes in the ambient environment near a device.

Android platform provides four sensors that let you monitor various enviromental properties. You can use these sensors to monitor **relative ambient humidity, illuminance, ambient pressure and ambient temperature** near an android powered device. All four environment sensors are hardware-based and are available only if a device manufacturer has built them into a device. With the exception of the light sensor, which most device manufacturers use to control screen brightness, environment sensors are not always available on devices. Because of this, it's particularly important that you verify at runtime whether an environment sensor exists before you attempt to acquire data from it.

Unlike most motion sensors and position sensors, which return a multi-dimensional array of sensor values for each SensorEvent, environment sensors return a single sensor value for each data event. For example, the temperature in °C or the pressure in hPa. Also, unlike motion sensors and position sensors, which often require high-pass or low-pass filtering, environment sensors do not typically require any data filtering or data processing.


## The sensors that are are supported on Andriod platform:
![image](https://user-images.githubusercontent.com/50220285/141855110-42ac1d55-8c30-4562-8e43-60f7fa5dff25.png)


## Using the light, pressure, and temperature sensors
The **raw data you acquire from the light, pressure, and temperature sensors usually requires no calibration, filtering, or modification**, which makes them some of the easiest sensors to use. To acquire data from these sensors you first create an instance of the **SensorManager class**, which you can use to get an instance of a physical sensor. Then you register a **sensor listener in the onResume() method**, and start **handling incoming sensor data in the onSensorChanged() callback method**.

## The following code goes over how this is done
![image](https://user-images.githubusercontent.com/50220285/141857526-07f57905-b431-4f53-a7fa-7e1ae400ffd9.png)

**You must always include implementations of both the onAccuracyChanged() and onSensorChanged() callback methods**. Also, be sure that you always **unregister** a sensor when an activity pauses. This prevents a sensor from continually sensing data and draining the battery.

## Implementation for the project
**The ways that these sensors could be implemented into the mobile project would be:**

**Ambient temperature sensor:** The temperature sensor can be used to record the current temperature at the location of the device. This could be displayed on the device so that the user could access this information. Antoher way that this could be used is on the maps dashboard where the tempature could be recorded for the certain places marked on the map.

**Light sensor:** The light sensor can be used to for controlling the screen brightness on the app. Depending on how bright or how dark the enviroment is this will change to suit the user.

**Pressure and humidity sensors:** The pressure and humidity sensors can be used for finding relative information about the weather at the current location of the device. Used with the temperature sensor, the user could get different information about weather.

**temperature:** This sensor acquires the temperature of the device. This could be used if the device was over heating and needed to be shut down for some reason.


## References
https://developer.android.com/guide/topics/sensors/sensors_environment#kotlin
https://developer.android.com/guide/topics/sensors/sensors_overview
