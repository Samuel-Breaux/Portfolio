# Portfolio
## Resume
```
                                                        Samuel Breaux
                                            SamuelWBreaux@gmail.com • 985-789-6302
                                    https://www.linkedin.com/in/samuel-breaux-2a7002259/


EDUCATION
Southeastern Louisiana University, Hammond, Louisiana
Bachelor of Science in Engineering Technology with a concentration in Mechatronics
GPA:3.49/4.00
Related Coursework:
Electronics I
Digital Computer Logic and Organization
Programmable Logic Controllers
Robotics and Automation
Digital Electronics
Engineering Graphics

RELEVANT EXPERIENCE
Raising Canes, Mandeville, Louisiana
Crew Mate, June 2022 - Dec 2022
●	Completed training for both kitchen and customer service work.
●	Attained skills in communication working in a team environment and handling customer transactions.
●	Learned problem solving methods dealing with customer and employee conflicts.

CLASS PROJECT EXPERIENCE
Glove Controlled Robotic Arm, Hammond, Louisiana
Senior Design, January 2024 - December 2024
●	Designed the glove PCB for the glove controlled robotic arm project.
●	Wrote the glove data transfer program and troubleshooted the robotic arm control program.
●	Had the role of glove design and troubleshooting. 

CAMPUS & COMMUNITY INVOLVEMENT
SLU Gaming
Secretary, Fall 2021 - Fall 2023
●	Organized the communication methods of the club and assisted in advertisement. Also attended all club leadership meetings to determine the use of the budget as well as scheduling of events.
●	Obtained organizational and managerial skills in a leadership role.

SKILLS
Computer: Microsoft Word, Excel, PowerPoint, VS Code, and Fusion 360
Language: C, C#, C++, and Python

HONORS AND AWARDS
Honor Roll, December 2021
President’s List, May 2022
President’s List, December 2022
President’s List, May 2023
President’s List, December 2023
President’s List, May 2024
President’s List, December 2024
```
## Senior Project
**Glove-Controlled Robotic Arm**

Southeastern Louisiana University

Engineering Technology 494-01

December 09, 2024

Participants: Samuel Breaux, Sean Bruce, & Chloe Hill

Coordinator: Dr. Ahmad Fayed

Advisor: Dr. Cris Koutsougeras

**Table Of Contents**


[TOC]




1. 
**Abstract**
	This project aims to create an innovative glove-controlled robotic arm designed to bridge the gap between human operators and remote environments. The use of a glove interface intends to act as an intuitive human-machine interface (HMI) for the robotic arm. Through finger-tracking and object-tracking methods, users can control a robotic system in real-time.



2. 
**Introduction**


<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")


*Figure 1: Physical System Overview*



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")


*Figure 2: Conceptual System Overview*

Over the course of this project, the group created a glove-controlled robotic arm by using various sensors to track data from the hand and then moving the arm based on this data. In the above figures are a physical and conceptual system overview showing how each component feeds into the system. The glove controller is a microcontroller receiving inputs from the inertial measurement unit, flex sensors, and a few buttons for safety and calibration. The robotic arm has a microcontroller, a servo driver, a stepper motor, an H-bridge, and five servo motors. The microcontroller of the robot acts as a receiver of the glove data and then moves the proper joints according to that input. The robotic arm also consists of multiple mechanical components that were designed and 3D printed for this project.



3. 
**Goals**
	The main goal of this project was to create an intuitive HMI that could control a simple robotic device. To accomplish this, the group made a set of measurable objectives known as deliverables to determine the success of the project. The deliverables can be seen in the following table:


<table>
  <tr>
   <td><strong>Deliverables</strong>
   </td>
  </tr>
  <tr>
   <td>Operator Glove assembly and robot controls system program (Chloe)
   </td>
  </tr>
  <tr>
   <td>3D printing and assembly of robotic arm (Sean)
   </td>
  </tr>
  <tr>
   <td>Operator Glove PCB design and communications program  (Samuel)
   </td>
  </tr>
  <tr>
   <td>Robotic arm assembly controlled by an operator glove capable of gripping and releasing an object
   </td>
  </tr>
</table>


*Figure 3: Deliverables*

By the end of this project, all of the deliverables were successfully completed. The specifics of each subsystem used to achieve the final result will be elaborated on in the system details.



4. 
**System **D**etails**


1. 
Glove Details
An ESP32 was chosen as the communication device for the glove due to its versatility, power efficiency and robust feature set. It offers both Wi-Fi and bluetooth capabilities, which are essential for seamless wireless communication with other devices. The ESP32’s dual-core processor ensures efficient handling of multiple tasks simultaneously, making it ideal for processing data from the flex sensor in real-time while managing communication. Its low power consumption is particularly valuable for wearable projects. Additionally, the ESP32 is well supported by a large development community, providing access to numerous libraries, tutorials, and resources, which simplifies the integration of sensors and communication protocols. Its small form factor and cost effectiveness make it an ideal choice for compact and reliable wearable technology.

The glove controller uses five flex sensors, five resistors, two buttons, an inertial measurement unit (IMU), and an ESP-WROOM-32 microcontroller. The five flex sensors in combination with the resistors make voltage dividers. The output voltage of these voltage dividers is fed to the GPIO pins of the microcontroller and acts as a signal that represents the angle of flexion of the flex sensor. For clarification, the following figure shows the details of a voltage divider.

*Figure 4: Voltage divider example*

The flex sensors are sewn to the glove so that this angle of flexion will correlate to the movements of the operator’s hand. The movements produced by these flex sensors were jittery due to noise. To overcome this obstacle, the group made a threshold value in the program and when this threshold was exceeded the robot would move at a stable speed. This way, the speed wasn’t fluctuating based on the noise. However, given more time, an impedance buffer could be added to the pcb design to reduce noise in the flex sensors. PID control could also be used to smoothly move between different speeds for more dynamic and fluid control. The IMU is responsible for keeping track of the hand orientation and communicates with the microcontroller using I<sup>2</sup>C. The specific IMU used in this model was the BNO085 by adafruit shown in Figure 5.

*Figure 5: BNO085 IMU*

The only other components used in this design were two simple push buttons for emergency stopping of the robot as well as a calibration button.  All of these components were connected via a printed circuit board designed by the group. The circuit schematic can be seen in the following figure.



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.png "image_tooltip")
 \
*Figure 6: Glove Controller PCB Schematic*

All of the sensors ultimately feed their data back to the ESP-WROOM-32 which has a program made to send out this information over ESP Now in a data structure consisting of floats for the flex sensors and angle data, and booleans for the buttons. The program can be seen in appendix A. This program is responsible for making the glove act as the sender of the two microcontrollers used in this system and its only job is to broadcast the data constantly being controlled by the ESP-WROOM-32. The methods of using this data to control the robot are found in the next section. The final assembly of the glove can be seen below in Figure 6 and acted as a successful robot controller in our project.



<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.jpg "image_tooltip")


*Figure 7: Final Glove Assembly*



2. 
Arm Details

        

<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.jpg "image_tooltip")


<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image6.jpg "image_tooltip")



        *      Figure 8: Assembled Robotic Arm	Figure 9: End-of-arm Tooling*


    The body of the robotic arm (Figure 8) is 3D printed and includes three degrees of freedom (joints) and an end-of-arm tooling. The end-of-arm tooling, the “claw” (Figure 9), has a body with a cross-style base with two holes for mounting. Higher on the right side of the body is a hole for an MG995 motor to be mounted face-up. A geared beam is attached to the servo head and supported by another beam above it. These beams control the motion of the right claw. This two-beam design is mirrored to the left claw to complete the scissoring motion that allows for gripping objects. 



<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image7.jpg "image_tooltip")


					*Figure 10: Wrist Bracket*



<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image8.jpg "image_tooltip")


					*Figure 11: Claw Mount Gear*



<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image9.jpg "image_tooltip")


					*Figure 12: Servo Gear*


    The “wrist” joint begins with mounting the claw to the claw mount gear (Figure 11). This gear is driven with a two-to-one gear ratio from two servo gears (Figure 12) attached to the MG995 servos. Two of these servos are mounted facing each other in the wrist bracket (Figure 10). By inverting the input controls of one servo and syncing their output, both motors move together in the same direction to produce double the torque while driving the bigger gear. 



<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image10.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image10.jpg "image_tooltip")


					*Figure 13: Arm Pin Half*


    The claw mount gear is held in place by two arm pins (Figure 13). The pins are 3D printed in halves with the flat face down so that the part is stronger on the z-axis. After gluing the two halves, the pins can be easily inserted and removed for any troubleshooting or testing of the individual assemblies. Otherwise, the pins hold the claw mount gear relatively centered while allowing just enough tolerance to rotate freely. 



<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image11.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image11.jpg "image_tooltip")


				*Figure 14: Shoulder Mount Bracket*



<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image12.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image12.jpg "image_tooltip")


*					Figure 15: Elbow Gear*



<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image13.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image13.jpg "image_tooltip")



                *Figure 16: Forearm Half*


    A similar design is implemented for the arm’s “elbow” joint. The forearm halves (Figure 16) are printed and assembled the same as the pins to increase z-axis strength. Once whole, the forearm connects the elbow gear (Figure 15), mounted to the shoulder mount bracket (Figure 14) by two more arm pins, to the wrist bracket. Then, through a two-to-one gear ratio to two servos, the arm’s length is manipulated.



<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image14.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image14.jpg "image_tooltip")


					*Figure 17: Arm Base*



<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image15.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image15.jpg "image_tooltip")


		*			Figure 18: Input Shaft*



<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image16.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image16.jpg "image_tooltip")



                    *Figure 19: Output Disk*


    The “shoulder” joint, or base, is manipulated by a Nema 17 Bipolar 2A stepper motor that rotates the input shaft to a cycloidal gear drive. This gear drive is a modified recreation of a tutorial in the blog post* Building a Cycloidal Drive with SOLIDWORKS *by Omar Youmis. The design’s size is decreased to twenty percent of the original to make it more relative to the size of the arm. The input shaft (Figure 18) includes a full disk for better support of the arm as well as a shorter shaft and a key hole to insert the shaft of the stepper motor. The output disk (Figure 19) has an increased diameter to also better the arm’s support.  The gear drive’s high gear reduction ratio allows for a high torque output to rotate the arm at an efficient rate. The shoulder mount bracket is mounted off-center on the output disk so the weight of the arm is more towards the center of the gear drive. Then, the entire gear drive is mounted on the arm base (Figure 17). The arm base is printed to support the weight of the arm vertically and horizontally with a square hole in the center for the stepper motor to sit in and a small channel at the bottom for the motor’s wires. Though, after its printing, the base had to be modified. The four small tabs atop the base needed removal, and one wall of the center hole needed slight adjustment because the wires were unable to be inserted properly during the insertion of the stepper motor.


    To control and power the arm, the arm’s ESP32 provides 3.3 Volts to and communicates with a Sunfounder PCA9685 servo driver. The 3.3 Volts powers the logic of the driver while an external 6 Volt power supply is wired in to provide power for the servos. As the ESP32 receives input, it translates it to the servo driver, and the driver directs the proper current as needed. Additionally, the ESP32 controls the stepper motor using an L293DNE H-bridge chip. The chip uses 5 Volts on the Vcc1 pin to manipulate the logic signals while 12 Volts is supplied to the Vcc2 pin to power the motor.



5. 
**Division of **W**orks**

<table>
  <tr>
   <td>Samuel Breaux
   </td>
   <td>Sean Bruce
   </td>
   <td>Chloe Hill
   </td>
  </tr>
  <tr>
   <td>
<ul>

<li>Research and design Glove Hardware</li>

<li>Assist in programming the glove and arm</li>
</ul>
   </td>
   <td>
<ul>

<li>Mechanics, movement, and design of the arm and claw</li>
</ul>
   </td>
   <td>
<ul>

<li>Making codes for arm and glove coordination</li>

<li>Assist with wiring arm</li>
</ul>
   </td>
  </tr>
</table>




6. 
**Challenges**
For research and design of the glove hardware, the main challenge has been in deciding which method to use for finger tracking. Last semester, the progress for the flex sensor glove took longer than expected so the team decided to explore other options. The main benefit of the other option our team is researching, which is using an exoskeleton with potentiometers measuring the angle joints, is that it offers higher precision than the flex sensor version. This is because the flex sensor design inherently has more variance in the resistance from small or insignificant movements. However, the exoskeleton design requires 3D printing which can be challenging with multiple small parts fitting together. Any warping or deformation of the parts can cause them to be unusable especially when parts fitting together have fairly low tolerances. This was especially noticeable in the claw design last semester. The 3d printing process for the arm has also been difficult throughout the entire process, often shifting the timeline to accommodate changes made to the design.

One of the main challenges in coding the glove was identifying the right libraries to use in Arduino IDE. For reasons that weren’t immediately clear, some libraries worked only on certain computers, which caused a lot of confusion and led to back-and-forth troubleshooting. This made it difficult to determine which libraries were compatible and reliable across different setups.

Soldering wires to a PCB presented several challenges, especially for beginners. One common difficulty was ensuring that the soldering iron was at the correct temperature. The soldering iron that was used did not specify if it was in Celsius or Fahrenheit so it was a guessing game. Another challenge was making sure that the joints were solid and clean so that they provided a good connection. Once the soldering was done from the PCB to the flex sensor they then needed to be sewn to the glove which presented more challenges. The flex sensors did not stay securely in place in their slits so many different methods were used to get them to not come undone. While sewing directly through the flex sensor seemed like an option it was avoided to prevent potential damage to the delicate components. 

The mechanics and movement of the arm are a challenge in their own right. The translation of power between motors has to be accurate and efficient to properly translate the data received from the glove as well as function as a whole. If one motor is implemented incorrectly, it will affect the stability and function of the other joints. Every motor has to support and move the weight of its relative joint, the joints and structure above it, and the payload putting strain on the entire arm.

Near the project's conclusion, the group had issues with the shoulder joint. The stepper motor was unable to turn the output disk when weight was applied. This is believed to be because of lack of support to the output disk. When weight was present, the motor’s shaft was liable to experience a load that was unconventional to its design. Due to lack of time, the stepper motor, along with the cycloidal gear drive, had to be removed from the final assembly. Also, the arm base could not prevent the arm from tipping over at full extension. To solve the output disk issue, the outer walls of the arm base can be raised up to the height of the disk, and an added lip with decent supports can allow the disk to rest so the weight is more on the base. As to solve the tipping issue, the arm base’s design can be widened for better weight distribution.



7. 
Materials

<table>
  <tr>
   <td colspan="2" ><strong>Robotic Arm</strong>
   </td>
  </tr>
  <tr>
   <td>Quantity
   </td>
   <td>Item
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>MG995 Servo Motor
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Nema 17 Bipolar Stepper Motor (17HS19-2004S1)
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>SunFounder PCA9685 Servo Driver
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>6 Volt Power Supply
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>ESP-WROOM-32
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>L293DNE Quadruple H-Bridge
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Breadboard
   </td>
  </tr>
  <tr>
   <td>As Needed
   </td>
   <td>Jumper Wires
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="2" ><strong>Control Glove</strong>
   </td>
  </tr>
  <tr>
   <td>Quantity
   </td>
   <td>Item
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Fabric Glove
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Custom PCB
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>BNO085 Inertial Measure Unit 
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Flex Sensor
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>ESP-WROOM-32
   </td>
  </tr>
  <tr>
   <td>10
   </td>
   <td>Wires
   </td>
  </tr>
</table>



## Appendix A: Glove Controller Program Code

#include &lt;Adafruit_BNO08x.h> // Import for IMU Module

#include &lt;esp_now.h>

#include &lt;WiFi.h>

// Pin Definitions

#define BNO08X_CS 10

#define BNO08X_INT 9

#define BNO08X_RESET -1

#define ERButton 24

#define calibButton 25

// IMU and ESP-Now Variables

uint8_t broadcastAddress[] = {0xFF, 0xFF, 0xFF, 0xFF, 0xFF};

Adafruit_BNO08x bno08x(BNO08X_RESET);

sh2_SensorValue_t sensorValue;

// Sensor Pins and Data Vectors

int sensorIDVector[5] = {34, 35, 32, 33, 25}; // P1–P5

float sensorDataVector[9] = {0, 0, 0, 0, 0, 0, 0, 0, 0};

// Flags and Configurations

bool ENABLE = true;

bool ER = false;

bool calibTime = false;

// Struct to Hold Data

typedef struct {

    bool calibTime;

    bool ER;

    float dataVector[9];

} data_vector;

data_vector data;

esp_now_peer_info_t peerInfo;

// Callback Function for ESP-Now

void OnDataSent(const uint8_t *mac_addr, esp_now_send_status_t status) {

    Serial.print("\r\nLast Packet Send Status:\t");

    Serial.println(status == ESP_NOW_SEND_SUCCESS ? "Delivery Success" : "Delivery Fail");

}

// Function to Initialize Sensor Reports

void setReports() {

    Serial.println("Setting desired reports");

    if (!bno08x.enableReport(SH2_GAME_ROTATION_VECTOR)) {

        Serial.println("Could not enable game vector");

    }

}

// Function to Update Sensor Data

void updateSensorData(int IDVector[5]) {

    // Handle Calibration Time

    if (data.calibTime) {

        delay(5000); // Wait for calibration and button release

    }

    // Toggle Emergency Reset

    if (digitalRead(ERButton)) {

        data.ER = !data.ER;

        delay(500); // Debounce delay

    }

    // Update Calibration and Analog Sensor Data

    data.calibTime = digitalRead(calibButton);

    for (int i = 0; i &lt; 5; i++) {

        data.dataVector[i] = map(analogRead(IDVector[i]), 0, 4095, 0, 265);

    }

    // Retrieve IMU Sensor Data

    if (bno08x.getSensorEvent(&sensorValue)) {

        if (sensorValue.sensorId == SH2_GAME_ROTATION_VECTOR) {

            data.dataVector[5] = sensorValue.un.gameRotationVector.real;

            data.dataVector[6] = sensorValue.un.gameRotationVector.i;

            data.dataVector[7] = sensorValue.un.gameRotationVector.j;

            data.dataVector[8] = sensorValue.un.gameRotationVector.k;

            // Debug Output

            Serial.print("Game Rotation Vector - r: ");

            Serial.print(data.dataVector[5]);

            Serial.print(", i: ");

            Serial.print(data.dataVector[6]);

            Serial.print(", j: ");

            Serial.print(data.dataVector[7]);

            Serial.print(", k: ");

            Serial.println(data.dataVector[8]);

        }

    }

}

// Function to Transmit Data via ESP-Now

void sendSensorData() {

    esp_err_t result = esp_now_send(broadcastAddress, (uint8_t *)&data, sizeof(data));

    if (result == ESP_OK) {

        Serial.println("Sent with success");

    } else {

        Serial.println("Error sending the data");

    }

    delay(50);

}

// Arduino Setup Function

void setup() {

    pinMode(calibButton, INPUT);

    pinMode(ERButton, INPUT);

    Serial.begin(115200);

    // Initialize ESP-Now

    WiFi.mode(WIFI_STA);

    if (esp_now_init() != ESP_OK) {

        Serial.println("Error initializing ESP-Now");

        return;

    }

    esp_now_register_send_cb(OnDataSent);

    // Register Peer

    memcpy(peerInfo.peer_addr, broadcastAddress, 6);

    peerInfo.channel = 0;

    peerInfo.encrypt = false;

    if (esp_now_add_peer(&peerInfo) != ESP_OK) {

        Serial.println("Failed to add peer");

        return;

    }

    // Initialize IMU

    if (!bno08x.begin_I2C()) {

        Serial.println("Failed to find BNO08x chip");

        while (1) {

            delay(10);

        }

    }

    Serial.println("Setup Complete");

}

void loop() {

    if (bno08x.wasReset()) {

        Serial.print("Sensor was reset. ");

        setReports();

    }

    if (ENABLE) {

        updateSensorData(sensorIDVector);

        sendSensorData();

    }

}


## Appendix B: Arm Controller Program Code

#include &lt;esp_now.h>

#include &lt;WiFi.h>

#include &lt;Wire.h>

#include &lt;Adafruit_PWMServoDriver.h>

#define SERVOMIN  90 // Minimum Servo

#define SERVOMAX  605 // Maximum Servo PWM Value

int motorFinger[4] = {9, 1, 2, 4};

int motorAngles[3] = {0, 0, 0}; // Angle of each motor or pair of motors

float lowerCalibs[4] = {0, 0, 0, 0}; // Lower calibration values. Doesn’t need initial values

float higherCalibs[4]; // Higher calibration values

bool calibrated = false; // Calibration flag

bool moving = false; // Moving flag

bool moveSynchro1; // Moving flag for joint 1

bool moveSynchro2; // Moving flag for joint 2

bool moveClawMotor; // Moving flag for joint 3

bool ER; // Emergency Stop

bool calibTime; // Used for recalibration

typedef struct data_vector { 

  bool calibTime; // Used for recalibration  

  bool ER; // Emergency Stop

  float dataVector[9];

} data_vector;

data_vector data; // Data vector received from the glove

float receivedData[9]; // Array for storing float data received from the glove

// Callback function executed when data is received

void OnDataRecv(const uint8_t *mac, const uint8_t *incomingData, int len) {

  int directionNumIndex = 7; // Index of IMU data with axis used to determine the direction of joint movements

  memcpy(&data, incomingData, sizeof(data));

  ER = data.ER;

  calibTime = data.calibTime;

  // Update the receivedData array

  for (int i = 0; i &lt; 9; i++) {

    receivedData[i] = data.dataVector[i]; 

    if (i == 0) receivedData[i] = 0;

    // Maps received data according to proper calibration values per finger

    if (calibrated && i &lt; 4) {

      receivedData[i] = map(receivedData[i], lowerCalibs[i], higherCalibs[i], 0, 100);

      receivedData[i] = constrain(receivedData[i], 0, 100);

    }

  }

  if (calibrated) {

    int aboveThresholdCount = 0;

    int largestIndex = 0;

    int largestValue = 0;

    for (int i = 0; i &lt; 4; i++) {

      if (receivedData[i] > largestValue) {

        largestValue = receivedData[i];

        largestIndex = i;

      }

      if (receivedData[i] > 60) aboveThresholdCount++;

    }

    if (aboveThresholdCount > 1) {

      updateMotors(largestIndex, directionNumIndex);

    } else {

      for (int i = 0; i &lt; 4; i++) updateMotors(i, directionNumIndex);

    }

  }

}

Adafruit_PWMServoDriver pwm = Adafruit_PWMServoDriver();

// Synchronizes two motors

int motorSync(int drivingMotor, int drivenMotor, int direction, int currentAngle, int speed = 5) {

  if (direction == 1) {

    currentAngle = constrain(currentAngle + speed, 5, 175);

    pwm.setPWM(drivingMotor, 0, angleToPulse(currentAngle));

    pwm.setPWM(drivenMotor, 0, angleToPulse(180 - currentAngle));

  } else {

    currentAngle = constrain(currentAngle - speed, 5, 175);

    pwm.setPWM(drivingMotor, 0, angleToPulse(currentAngle));

    pwm.setPWM(drivenMotor, 0, angleToPulse(180 - currentAngle));

  }

  delay(50);

  return currentAngle;

}

// Smooth motor movement

int motorSmooth(int motor, int direction, int currentAngle, int speed = 10) {

  if (direction == 1) {

    currentAngle = constrain(currentAngle + speed, 5, 175);

    pwm.setPWM(motor, 0, angleToPulse(currentAngle));

  } else {

    currentAngle = constrain(currentAngle - speed, 5, 175);

    pwm.setPWM(motor, 0, angleToPulse(currentAngle));

  }

  delay(50);

  return currentAngle;

}

// Updates motor values based on received data

void updateMotors(int finger, int directionNumIndex) {

  int triggerThreshold = 60;

  if (receivedData[finger] > triggerThreshold) {

    if (finger == 1) {

      moveSynchro1 = true;

      moveSynchro2 = false;

      moveClawMotor = false;

    } else if (finger == 2) {

      moveSynchro2 = true;

      moveSynchro1 = false;

      moveClawMotor = false;

    } else if (finger == 3) {

      moveClawMotor = true;

      moveSynchro1 = false;

      moveSynchro2 = false;

    }

  } else {

    moveClawMotor = false;

    moveSynchro1 = false;

    moveSynchro2 = false;

  }

}

// Calibrates flex sensor values for each finger

void calibration() {

  Serial.println("Hold hand open");

  delay(500);

  Serial.println("3");

  delay(1000);

  Serial.println("2");

  delay(1000);

  Serial.println("1");

  delay(1000);

  for (int i = 0; i &lt; 4; i++) {

    lowerCalibs[i] = receivedData[i];

  }

  Serial.println("Hold hand closed");

  delay(500);

  Serial.println("3");

  delay(1000);

  Serial.println("2");

  delay(1000);

  Serial.println("1");

  delay(1000);

  for (int i = 0; i &lt; 4; i++) {

    higherCalibs[i] = receivedData[i];

  }

  calibrated = true;

}

// Converts angle to PWM signal

int angleToPulse(int angle) {

  return map(angle, 0, 180, SERVOMIN, SERVOMAX);

}

void setup() {

  Serial.begin(115200);

  pwm.begin();

  pwm.setPWMFreq(60);

  pwm.setPWM(1, 0, angleToPulse(5));

  pwm.setPWM(0, 0, angleToPulse(175));

  pwm.setPWM(3, 0, angleToPulse(175));

  pwm.setPWM(2, 0, angleToPulse(5));

  pwm.setPWM(4, 0, angleToPulse(0));

  WiFi.mode(WIFI_STA);

  if (esp_now_init() != ESP_OK) {

    Serial.println("Error initializing ESP-NOW");

    return;

  }

  esp_now_register_recv_cb(OnDataRecv);

  calibration();

}

void loop() {

  int direction = (receivedData[6] >= 0.6) ? 1 : 0;

  Serial.println(direction);

  if (calibTime) calibration();

  if (ER) {

    Serial.println("Robot will not move until ER is reset");

  } else if (moveSynchro1) {

    motorAngles[0] = motorSync(1, 0, direction, motorAngles[0]);

  } else if (moveSynchro2) {

    motorAngles[1] = motorSync(3, 2, direction, motorAngles[1]);

  } else if (moveClawMotor) {

    motorAngles[2] = motorSmooth(4, direction, motorAngles[2]);

  }

}

References


    Gass, Daniel. “Robot Arm Automation.” *Arduino Project Hub*, 7 January 2022, https://projecthub.arduino.cc/danielgass/robot-arm-automation-c4e0cb. Accessed 28 February 2024.


    McCurdy, Iain. “DIY Bend Sensor.” *Iain McCurdy*, 2016, http://iainmccurdy.org/diy/bendsensor/bendsensor.html. Accessed 28 February 2024.


    Mouser Electronics. *Mouser Electronics*, https://www.mouser.com/ProductDetail/Amphenol-Piher/PT15NH06-202A2020?qs=%2FzPWuUUsT7MKz1MDcCOWCQ%3D%3D. Accessed May 2024.


    Mouser Electronics. “PT15NH06-202A2020.” *Mouser Electronics*, https://www.mouser.com/ProductDetail/Amphenol-Piher/PT15NH06-202A2020?qs=%2FzPWuUUsT7MKz1MDcCOWCQ%3D%3D. Accessed 6 May 2024.


    3DPrintIt. “3D Printed Powered Exoskeleton Hands (Upgrade v1).” *Thingiverse*, https://www.thingiverse.com/thing:952267. Accessed May 2024.


    Toglefritz. “Build a Giant 3D Printed Robot Arm : 83 Steps (with Pictures).” *Instructables*, 2017, https://www.instructables.com/Build-a-Giant-3D-Printed-Robot-Arm/. Accessed 28 February 2024.


    Wu, Changcheng et al. “Development of a Low-Cost Wearable Data Glove for Capturing Finger Joint Angles.” *NCBI*, 30 June 2021, https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8304804/. Accessed 28 February 2024.


    Younis, Omar. “Building a Cycloidal Drive with SOLIDWORKS.” 2014. *Dassault Systèmes*, https://blogs.solidworks.com/teacher/2014/07/building-a-cycloidal-drive-with-solidworks.html.

## Programming
### ELO Program 
Simple program written to practice basic object oriented programming skills
#### Player Class File
```
#include <cmath>
#include <iostream>
#include <fstream>
#include <sstream>
#include <vector>
using namespace std;

int k = 32;
class Player{
    private:
        int elo;
        string name;

    public:

        // Constructor to create a player or load an existing player by name
        Player(string nm) {
            if (!loadPlayer(nm)) {  // Try to load the player
                name = nm;
                elo = 800;
                savePlayer();  // Save the new player if not found
            }
        }

        // Constructor to create a player with a specific ELO rating or load existing player
        Player(string nm, int rating) {
            if (!loadPlayer(nm)) {  // Try to load the player
                name = nm;
                elo = rating;
                savePlayer();  // Save the new player if not found
            }
        }

        void setName(string nm){
            name = nm;
        }

        void setELO(int newELO){
            elo = newELO;
        }

        string getName(){
            return name;
        }

        int getELO(){
            return elo;
        }

        void displayInfo(){
            cout << getName() << ": " << getELO() << endl;
        }

       // Save player to file (update if player exists or add new player to file)
    void savePlayer() {
        vector<string> players;  // Vector to hold all players' data
        ifstream file("Players.txt");
        string line;
        bool playerExists = false;
        
        // Read all players and check for an existing player with the same name
        while (getline(file, line)) {
            string playerName = line; // First line is player name
            if (getline(file, line)) { // Second line is player ELO
                int playerElo = stoi(line);
                if (playerName == name) {
                    playerExists = true;
                    players.push_back(name + "\n" + to_string(elo));  // Update Elo for this player
                } else {
                    players.push_back(playerName + "\n" + to_string(playerElo)); // Insert old player data if no changes are needed
                }
            }
        }
        file.close();

        // If the player already exists, overwrite the file with updated data
        ofstream outFile("Players.txt", ios::trunc);  // Open in trunc mode to overwrite the file
        for (const string& playerData : players) {
            outFile << playerData << endl;
        }

        // If player didn't exist, append new player to the file
        if (!playerExists) {
            outFile << name << endl << elo << endl;
        }
        outFile.close();
    }

        bool loadPlayer(string playerName) {
            ifstream file("Players.txt");
            string line;
            bool playerFound = false;
    
            while (getline(file, line)) {
                string nameFromFile = line; //First line is player name
                cout << nameFromFile << endl;
                if (getline(file, line)) {  // Second line is player ELO
                    int eloFromFile = stoi(line);
                    if (nameFromFile == playerName) {
                        name = nameFromFile;
                        cout << name << " loaded from file" << endl;
                        elo = eloFromFile;
                        playerFound = true;
                        break;
                    }
                }
            }
            file.close();
            return playerFound;
        }

};

void eloCalculation(Player &A, Player &B, int AScore, int BScore){
    float expectedAScore = 1/(1+pow(10,(A.getELO()-B.getELO())/400));
    float expectedBScore = 1/(1+pow(10,(B.getELO()-A.getELO())/400));
    cout << "Expected A Score: " << expectedAScore << endl;
    cout << "Expected B Score: " << expectedBScore << endl;
    
    A.setELO(A.getELO() + k*(AScore - expectedAScore));
    B.setELO(B.getELO() + k*(BScore - expectedBScore));
    A.savePlayer();
    B.savePlayer();
}
```
#### Main File
```
#include <iostream>
#include <fstream>
#include "C:\Users\Intern Samuel\Desktop\C Workspace\ELO_Math.h"

using namespace std;



int main(){
    Player Player1 = Player("P1");
    Player Player2 = Player("P2");
    Player1.displayInfo();
    Player2.displayInfo();
    eloCalculation(Player1, Player2, 1, 0);
    Player1.displayInfo();
    Player2.displayInfo();

    return 0;
}
```
#### Save File
```
P1
816
P2
688
```
## CAD Work
### Final Project Fan Design
![Final Project Drawing](https://github.com/user-attachments/assets/ff8eaba7-9001-492f-a379-8945b36a60c3)
![Final Project Drawing (1)](https://github.com/user-attachments/assets/4202747f-6b8e-4473-b59b-5e5a283df8b4)
![Final Project Drawing (2)](https://github.com/user-attachments/assets/af035be5-4aa7-40d1-bb31-1db28757bce4)
![Final Project Drawing (3)](https://github.com/user-attachments/assets/f6b018b8-ae79-4ded-8537-398787639338)
![Final Project Drawing (4)](https://github.com/user-attachments/assets/990eaecd-c497-41f6-8b4b-569777ab32d0)
![Final Project Drawing (5)](https://github.com/user-attachments/assets/5006fc7f-1f95-452b-93d5-25ea726888f9)
![Final Project Drawing (6)](https://github.com/user-attachments/assets/7c3c4bec-75da-4fea-8617-7f0a7e840392)
![Final Project Drawing (7)](https://github.com/user-attachments/assets/8ba2a1a0-0e57-4386-8d7c-678f13235bf4)
