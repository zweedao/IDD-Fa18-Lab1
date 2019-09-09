# IDD-Fa18-Lab1: Blink!

**A lab report by John Q. Student**

**Fork** this repository to get a template for Lab 1 for *Developing and Designing Interactive Devices* at Cornell Tech, Fall 2018. You should modify this `README.md` file to delete this paragraph and update below. As the lab asks:

> Include your responses to the bold questions on your own fork of the lab activities. Include snippets of code that explain what you did. Deliverables are due next Tuesday. Post your lab reports as `README.md` pages on your GitHub, and post a link to that on your main class hub page.

We've copied the questions from the lab here. Answer them below!

## Part A. Set Up a Breadboard

![Zwee's breadboard](/board_1.JPG)

## Part B. Manually Blink a LED

**a. What color stripes are on a 100 Ohm resistor?**
2 red stripes & 1 black stripe.

![Resistor](/resistor.jpg)

**b. What do you have to do to light your LED?**

- Connect LED to pin 9.

![Light up the LED](/board_2.jpg)

- Upload this code to Arduino to send 5V to my LED:

<pre><code>
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(9, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(9, HIGH);   // turn the LED on (HIGH is the voltage level)
}
</code></pre>

- Press the button

## Part C. Blink a LED using Arduino

### 1. Blink the on-board LED

**a. What line(s) of code do you need to change to make the LED blink (like, at all)?**
Nothing actually. The "Blink" sample code works fine.

<pre><code>
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(100);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(100);                       // wait for a second
}
</code></pre>

**b. What line(s) of code do you need to change to change the rate of blinking?**
Change the values in the 2 `delay(100)` lines above. The higher the number, the slower the blinking rate.

**c. What circuit element would you want to add to protect the board and external LED?**
Probably a resistor to prevent short circuit.
 
**d. At what delay can you no longer *perceive* the LED blinking? How can you prove to yourself that it is, in fact, still blinking?**
At `delay` = 10, I can't perceive the blinking. Gradually increase the `delay` to 15, I can perceive a very rapid blinking. So at `delay` = 10, it must have been blinking.

**e. Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md.**
[Blink code](/Blink_copy.ino)

### 2. Blink your LED

**Make a video of your LED blinking, and add it to your lab submission.**

![Blink video](/blink.mov)


## Part D. Manually fade an LED

**a. Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?**


## Part E. Fade an LED using Arduino

**a. What do you have to modify to make the code control the circuit you've built on your breadboard?**

**b. What is analogWrite()? How is that different than digitalWrite()?**


## Part F. FRANKENLIGHT!!!

### 1. Take apart your electronic device, and draw a schematic of what is inside. 
We take apart a smart switch, which when a device is plugged into it, the user can turn on/off the device remotely via Wifi/internet.

**a. Is there computation in your device? Where is it? What do you think is happening inside the "computer?"**
Yes, it's on the PCB. I think the "computer" basically takes in the instructions from user, then instruct the other components whether or not to let the 120V voltage flow through to the plugged-in device.

**b. Are there sensors on your device? How do they work? How is the sensed information conveyed to other portions of the device?**
Yes. There are wifi receiver and wifi transmitter that receive/transmit instructions from user. The sensed information is sent to the "computer", which will compute and instruct other portions of the device.

**c. How is the device powered? Is there any transformation or regulation of the power? How is that done? What voltages are used throughout the system?**
The device is powered by directly plugging it to 110V wall socket. There seems to be transformation/regulation using several big capacitors. 

**d. Is information stored in your device? Where? How?**
Information must have been stored in the "computer" chip, which must have integrated memory. This allows the smart switch to save user's instruction (e.g. automatically turn on device at 8am).

### 2. Using your schematic, figure out where a good point would be to hijack your device and implant an LED.

**Describe what you did here.**



### 3. Build your light!

**Make a video showing off your Frankenlight.**



**Include any schematics or photos in your lab write-up.**
