<p align="center">
  <img src="images/profile_photo.jpg" width="150">
</p>

Hi! I'm **Siang Peng**, a senior in ECE at Cornell.<br>
This page will be used to share my coursework in Fast Robots. I hope this page can help future students better understand the requirements of these labs and provide some guidance.<br>
> ⚠️ **Note:** I am using **Windows 11**. If your system is different, check what applies to your system.

# Lab 1: The Artemis Board and Bluetooth

## Parts
- SparkFun RedBoard Artemis Nano × 1  
- USB-C cable × 1  

<p align="center">
  <img src="images/lab1/parts.jpg" width="400">
</p>

---

## Prelab

1. Get Arduino IDE at [Arduino IDE](https://docs.arduino.cc/software/ide/)  
2. Open Arduino IDE → **File → Preferences → Additional Boards Manager URLs**  

<p align="center">
  <img src="images/lab1/1.png" width="400">
</p>

3. Paste the following URL in a separate line (if you have previously added other files) and save changes:  
<code>https://raw.githubusercontent.com/sparkfun/Arduino_Apollo3/main/package_sparkfun_apollo3_index.json</code>

<p align="center">
  <img src="images/lab1/2.png" width="400">
</p>

4. Go to **Tools → Board → Board Manager**  

<p align="center">
  <img src="images/lab1/3.png" width="400">
</p>

5. Search **“Apollo3”** and install **SparkFun Apollo3 Boards**  

<p align="center">
  <img src="images/lab1/4.png" width="400">
</p>

> Till now, we have completed all preparations for Lab 1A.

---

## Lab 1A

### Task 1: Connect Artemis board to the computer
First, I hooked the Artemis board up to my laptop. Then I clicked on port selection on the top left corner of Arduino IDE window, and clicked on the COM port that shows up. For me it is COM7; if you have trouble detecting your chip, try a different port on your device.  

<p align="center">
  <img src="images/lab1/5.png" width="400">
</p>

---

### Task 2: Make the built-in LED on board blink
Click **File → Examples → 01.Basics → Blink**  

<p align="center">
  <img src="images/lab1/6.png" width="400">
</p>

A new Arduino IDE window pops up. Make sure the correct board and port are selected, then click **Upload**.  

Now you should be able to see the built-in LED on board blinking blue.  

<!-- Video.1 placeholder -->
<p align="center">
  <!-- Replace with video when available -->
  <video width="400" controls>
    <source src="videos/video1.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</p>

<p align="center">
  <img src="images/lab1/7.png" width="400">
</p>

> If not, check if you have the correct board and port selected.

---

### Task 3: Type in the Serial Monitor
Go to **File → Examples → Apollo3 → Example4_Serial**. Click on the Serial Monitor icon on the top right corner of the Arduino IDE window.  

<p align="center">
  <img src="images/lab1/8.png" width="400">
</p>

Before clicking **Upload**, check if the baud rate of the Serial Monitor matches what it is defined in the script.  
> Baud rate is the number of signal changes per second; if those two do not match, you will receive **garbled text**.  

<p align="center">
  <img src="images/lab1/9.png" width="400">
</p>

Now type any text in the Serial Monitor, you should see it echo back like this:  

<!-- Video.2 placeholder -->
<p align="center">
  <video width="400" controls>
    <source src="videos/video2.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</p>

---

### Task 4: Read temperature
Go to **File → Examples → Apollo3 → Example2_analogRead**.

> Note: by default the script uses <code>int temp_raw = analogReadTemp()</code>, which gives **raw ADC counts** from the temperature sensor.  
> **ADC value** is the number the sensor outputs after converting its voltage to a digital number.

Later in Lab 1B, we will use <code>float temp_f = getTempDegF()</code> to read **actual temperature values**.  

Now click **Upload**. You should see the Serial Monitor continuously outputting various sensor and voltage readings, including the ADC value from the temperature sensor.  

> By placing your board near the laptop **air vent**, you should see the value goes up, assuming your computer is blowing out hot air.

<!-- Video.3 placeholder -->
<p align="center">
  <video width="400" controls>
    <source src="videos/video3.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</p>

---

### Task 5: Test microphone
Go to **File → Examples → PDM → Example1_MicrophoneOutput**, then click **Upload**.  

You should see the Serial Monitor continuously outputting the **loudest frequency**.  

> The white noise in the lab was quite loud, so try testing at home instead.

<!-- Video.4 placeholder -->
<p align="center">
  <video width="400" controls>
    <source src="videos/video4.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</p>
