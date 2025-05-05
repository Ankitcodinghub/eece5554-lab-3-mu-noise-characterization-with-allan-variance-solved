# eece5554-lab-3-mu-noise-characterization-with-allan-variance-solved
**TO GET THIS SOLUTION VISIT:** [EECE5554 LAB 3-MU Noise Characterization with Allan Variance Solved](https://www.ankitcodinghub.com/product/eece5554-lab-3-mu-noise-characterization-with-allan-variance-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;95066&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;EECE5554 LAB 3-MU Noise Characterization with Allan Variance Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
MU Noise Characterization with Allan Variance

</div>
</div>
<div class="layoutArea">
<div class="column">
Goals

We would like to understand how to characterize and choose IMU sensors for different robotic applications. As part of the exercise we will write a device driver for the IMU and use that to collect data and analyze it.

Readings

We have discussed sensor calibration and sensor stochastic characterization. The Vectornav whitepaper on the subject is included so that you can refresh your memory.

Hardware / Sensors:Vectornav VN-100 IMU. The user manual for the sensor is provided.

Hardware Setup

Imu udev rules Standard Ubuntu is not designed for roboti application and for fast sensors it may not behave as we want it to. There may be latency in terms of its response to the sensor. There are a set of files under /etc/udev that dictate how Ubuntu will react to certain sensors.

To make the VN-100 plug &amp; play and to address Ubuntu USB latency issues we can do the following

Connect your imu and type the following command in the terminal

$ dmesg | grep vn100

If you do not know what those commands mean, check out Linux tutorial.

You will see your sensor attributes including product id and vendor id. If these values differ from the values below, change them in your 50-VN-100.rules file accordingly.

<ol>
<li>As Sudo create a file under /etc/udev/rules.d called 50-VN-100.rules with the following</li>
<li>Ubuntu’s default latency of 16ms cause issues with high rate sensors, this can be solved by adding the following UDEV rules as 49-USB-LATENCY.rules</li>
</ol>
<pre>ACTION=="add", SUBSYSTEM=="usb-serial", DRIVER=="ftdi_sio", ATTR{latency_timer}="1"
</pre>
3. Once the rules have been added, to get udev to recognize the rule, run the following command:

Finally unplug and replug the VN-100 to have it work with the new rules.

You can verify the applied settings with below command, should report 1 on success.

</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>KERNEL=="ttyUSB[0-9]*", ACTION=="add", ATTRS{idVendor}=="1d6b", ATTRS{idProduct}=="0002",
                                     MODE="0666", GROUP="dialout"
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>sudo udevadm control --reload-rules &amp;&amp; sudo service udev restart &amp;&amp; sudo udevadm trigger
</pre>
</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
EECE 5554 Robotics Sensing and Navigation Spring 2022 $ cat /sys/bus/usb-serial/devices/&lt;ttyUSB0 your device path&gt;/latency_timer

Write a device driver for IMU (individual) and do stationary noise analysis

Open serial port with 115200 baudrate. Configure your IMU to output data at 200Hz for this lab.

Parse $vnymr string, to get accel, gyro, orientation (roll, pitch, yaw) and magnetometer data. Refer to sensor user_manual.

Use the standard ROS sensor_msgs/IMU to publish the above data. Convert the above Yaw, Pitch, Roll data into quaternions and publish it as orientation in the same imu msg. Use ROS sensor_msgs/MagneticField to publish magnetometer data.

Begin collecting a time series data (rosbag) for the 3 accelerometers, 3 angular rate gyros, 3- axis magnetometers. Collect at least 10-15 min of data with the instrument stationary and as far away as possible from your computer.

Plot each time series in your report and figure out the noise characteristics of each of the values (mean and standard deviation) reported by the IMU.

Allan Variance Data collection and Analysis

For this part we only need to collect one set of data for each team – collect roughly 5 hours worth of stationary IMU data at a location that is not subject to vibrations (passing trains, building sway etc).

The following MathWorks webpage provides code that you can use to analyze your data for Allan variance. We do not need any further analysis for Allan Variance other than that illustrated in this code.

https://www.mathworks.com/help/nav/ug/inertial-sensor-noise-analysis-using-allan- variance.html

You need to analyze this data using the Matlab functions and should be able to answer the following questions.

<ol>
<li>What kind of errors/sources of noise are present?</li>
<li>How do we model them? Where do we measure them? Can you relate your
measurements to the datasheet for the VN100?
</li>
</ol>
How to Submit Lab_3

<ol>
<li>In your class repo ‘EECE5554_RoboticsSensing’, create a directory called LAB3</li>
<li>Copy the ros driver package used for this assignment under LAB3.</li>
<li>Inside LAB3. create a sub-directory called ‘analysis’</li>
<li>Place your report in pdf format also in the analysis directory. Your report includes
analysis for both the stationary data you collected individually, as well as the Matlab

analysis on the data on Allan variance collected as a team.
</li>
<li>Place any matlab / python code you used to generate and plot your noise parameters in
this directory as well.
</li>
</ol>
</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
EECE 5554 Robotics Sensing and Navigation Spring 2022 Your repo structure should look similar to

‘&lt;Path_to_repo&gt;/EECE5554_RoboticsSensing/LAB2/src/&lt;your_imu_ros_driver files&gt;’ ‘&lt;Path_to_repo&gt;/EECE5554_RoboticsSensing/LAB2/src/analysis/&lt;your analysis files&gt;’ ‘&lt;Path_to_repo&gt;/EECE5554_RoboticsSensing/LAB2/src/analysis/report.pdf’

6. Push your local commits to (remote) gitlab server. You can verify this by visiting gitlab.com and making sure you can see the commit there.

Everyone in the team needs to write their own device driver for the IMU. Make sure everyone gets a fair amount of sensor time to test their imu driver, and to analyze sensor noise. You can use the emulator to write your driver even when you do not physically have access to the device. We have provided a sample IMU data file for your use.

Analysis on the collected dataset, should be done individually.

</div>
</div>
</div>
