# Introduction
Transportation operations in various industries, warehouses, restaurants and other sectors often face challenges related to transportation movement, including its return to the original point, or the need to facilitate the transportation of heavy materials. These challenges are accompanied by high labor costs and the demand for efficient logistics services. To overcome these obstacles, we harnessed the power of the Internet of Things (IOT) to develop an innovative project that integrates a mobile base with sensors, a microcontroller and MQTT communications. Our primary goal is to provide a versatile and efficient solution that simplifies the process of transporting goods and other resources, reduces labor costs, and facilitates the transport of heavy and bulky items. By taking advantage of advanced motion algorithms made by ourselves (autonomous mode: - user-controlled mode-	Grid-Based Navigation Mode), our project enables the mobile phone base to move and adapt to dynamic conditions. This intelligent mobility capability enhances movement efficiency and ensures safe transportation of goods and resources. The sturdy construction of the movable base and powerful motor system allows it to easily carry large loads that would otherwise be a challenge to human workers. By reducing reliance on manual labour, our project contributes significantly to saving costs and enhancing safety in the workplace. Our IoT-based project addresses the challenges facing transportation operations across various sectors. By simplifying resource movement, reducing labor costs, and streamlining logistics, we improve efficiency and safety while optimizing resource utilization. The integration of IoT technology provides real-time data, advanced algorithms and seamless connectivity, revolutionizing the way stores and other sectors move.
## How it works ? 
Our project include three various operational modes, each offering unique functionality and control capabilities for our moving base:

 1-	User-Controlled Mode

2-	Autonomous Mode

3-	Grid-Based Navigation Mode

## Sequence diagrams 
This image is a sequence diagram for a Moving Base Project, which illustrates the interactions between different components and entities involved in three distinct modes of operation: User-Controlled Mode, Autonomous Mode, and Grid-Based Navigation Mode. Here's a detailed explanation of the diagram:

Components and Entities:
User: The person interacting with the system.
Node-RED: A flow-based development tool for visual programming.
MQTT Broker: A messaging protocol for small sensors and mobile devices.
ESP8266: A microcontroller with Wi-Fi capability.
Arduino: A microcontroller used to control hardware.
Ultrasonic Sensors: Sensors used to detect obstacles.
Modes of Operation:

User-Controlled Mode:
User sends a command to Node-RED.
Node-RED publishes the command to the MQTT Broker.
The MQTT Broker transmits the command via MQTT to the ESP8266.
The ESP8266 forwards the command to the Arduino.
The Arduino executes the command to move forward, backward, turn left, or turn right.

Autonomous Mode:
The Arduino reads sensor data from the Ultrasonic Sensors.
The sensor data is sent back to the Arduino.
The Arduino checks for obstacles.
If an obstacle is detected:
The Arduino stops, moves backward, turns left or right.
Adjusts the path accordingly.
The adjusted path is executed.

Grid-Based Navigation Mode:
User enters coordinates into Node-RED.
Node-RED publishes the coordinates to the MQTT Broker.
The MQTT Broker transmits the coordinates via MQTT to the ESP8266.
The ESP8266 forwards the coordinates to the Arduino.
The Arduino calculates the target position.
The Arduino reads sensor data from the Ultrasonic Sensors.
The sensor data is sent back to the Arduino.
If an obstacle is detected:
The Arduino adjusts the path.
The Arduino moves to the target position.

![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/7b9d4d09-6723-410d-b60d-e9efb4888180)


## User-Controlled Mode
In this mode, users interact with the moving base through Node-RED, inputting commands that are transmitted to the Arduino via MQTT. This seamless communication pathway enables users to remotely control the base's actions and functionalities. The MQTT protocol facilitates data transmission from Node-RED to an ESP8266 module, which acts as an intermediary before forwarding commands to the Arduino for execution

## 	Autonomous Mode
The Arduino operates autonomously when activated, and enables the mobile base to navigate its environment autonomously. Using pre-defined algorithms, the Arduino analyzes sensor inputs, detects obstacles, and adjusts the base's path as needed, without the need for constant external intervention. This independent function ensures smooth and efficient movement, enhancing the base's adaptability and operational efficiency.

 ## 	Grid-Based Navigation Mode
In the third mode, the moving base environment is divided into a matrix grid, allowing users to specify precise destinations by entering coordinates such as [0] [2]. Users enter these coordinates via Node-RED, and the data is transmitted to the Arduino through MQTT and the ESP8266 module. The Arduino interprets the coordinates and directs the base to the specified point within the array, providing users with precise control of the base's movement within the environment.

## Working
### Flowchart mode (User-Controlled /Autonomous )
This image is a flowchart diagram illustrating the decision-making process for controlling a moving base project. The flowchart details how the system processes user inputs to determine whether to operate in autonomous mode or manually based on specific commands. Here’s a step-by-step explanation:
1.	Start:
 The process begins at the "start" point.
2.	User Input via Node-RED:
The user provides input through Node-RED, which is a flow-based development tool for visual programming.
3.	Autonomous Decision:
 The system checks if the input command is for autonomous operation.
Yes: If autonomous, it proceeds to call the autonomous function.
No: If not autonomous, it moves to manual operation decisions.
4.	Manual Operation Decisions:
The system evaluates the specific direction commands:
	Forward?: Checks if the command is to move forward.

	Yes: Calls the moveForward(); function. 

	No: Proceeds to the next check.


	Right?: Checks if the command is to turn right.

	Yes: Calls the TurnRight(); function.
	No: Proceeds to the next check. 


	 Left?: Checks if the command is to turn left.

	Yes: Calls the turnLeft(); function.
	No: Proceeds to the next check. 

	Move Backward: If none of the above commands are given, it defaults to moving backward by calling the moveBackward(); function.

5.	Loop Back to User Input:
After executing any of the commands (whether autonomous or manual), the process loops back to await new user input via Node-RED, thus continuing the cycle.

![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/abb0c595-4eb6-4409-acf6-ba8391292c29)

### User-Controlled Mode

![Userm](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/28590622-57cc-44cd-ab28-06a7a4225df5)
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/6cf1536b-dcb4-47a5-b1e2-8b09ec1a032e)
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/23a8e61d-02e3-4bf7-a26a-1d56d8b610de)
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/44b09b0a-7dbe-45ff-bea3-faa0a95b590b)

### Autonomous Mode
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/631a3ea4-faa8-4aba-b3eb-2404731d1df7)

![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/31fba074-b928-46dd-9345-7ad3ef78949e)
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/3760425f-62df-4cd5-95cd-e140915ad658)


## Grid-Based Navigation Mode
### Flowchart mode (Grid-Based Navigation )
This image is a detailed flowchart illustrating the algorithm for navigating a moving base or robotic car from an initial position to a target position while avoiding obstacles. Here's a step-by-step explanation of the flowchart:
1.	Start:
The process begins at the "start" point.

2.	Initial Points and User Input:

The system starts with initial points [0][0], and the user enters target points [i][j].

3.	Check User Input:
The system checks if the current position car[i][j] matches the user input.
Yes: If they match, the system updates car[i][j] to the user input.
No: Proceeds to check if the car has reached the target.
4.	Check Target Position:
The system checks if the current position car[i][j] is equal to the target [i][j].
Yes: The target is reached, the process may end or loop back.
No: Proceeds to the next decision point.
5.	Determine Direction to Target:
Checks if the difference between the target and current position in either row or column is positive to determine the direction.
Yes: Moves towards increasing row or column.
No: Checks for obstacles and adjusts accordingly.
6.	Obstacle Detection and Distance Reading:
The system reads distances from sensors (front, right, left, back) to detect obstacles.
	Read Front Distance: If no obstacle, increases column (increaseCol();). If an obstacle, checks for alternatives.

	Right Obstacle?: Reads right distance and decides whether to increase row. 


	Left Obstacle?: Reads left distance and decides whether to decrease row. 

	Read Back Distance: If no obstacle, decreases column (decreaseCol();). If an obstacle, checks for alternatives. 


7.	Adjust Position: 

Based on obstacle detection, the system decides to:
	Increase Column: Move forward if no front obstacle.
	Increase Row: Move to the right if no right obstacle.
	Decrease Row: Move to the left if no left obstacle.
	Decrease Column: Move backward if no back obstacle. 

8.	Loop or Stop:

If the target is reached or an obstacle prevents further movement, the system stops (MoveStop();).
If not, the system loops back to check and update the position, continuing the navigation process.


![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/4659e904-6798-4e6a-995d-40ba448b463b)

### How to construct the matrix and dimensions

This image is a schematic representation of a grid-based navigation system for a car within a room. The diagram includes the car's dimensions, room dimensions, and the calculation for the number of blocks in the grid. Here's a detailed explanation of each component in the diagram:
Diagram Components:

1.	Car Dimensions:
   
  **Car Length (L): 0.42 meters**

  **Car Width (W): 0.42 meters**

3.	Room Dimensions:
   
  **Room Length (RL): 2.10 meters**

  **Room Width (RW): 2.10 meters**

5.	Grid Representation:
   
  The room is divided into a grid based on the car's dimensions.
  Each block in the grid represents a space that can fit the car.

7.	Grid Calculations:
   
  R (Number of Rows): Calculated by dividing the room length (RL) by the car length (L).
  
  **R=RLL=2.100.42=5**

  C (Number of Columns): Calculated by dividing the room width (RW) by the car width (W).'
  
 **C=RW/W=2.10/0.42=5**

9.	Speed and Time Calculations:

  S (Speed): Represented as distance divided by time 
  
  **S=d/t**
  
  B (Time for One Block): The time it takes for the car to move one block in the grid.

  **B=CarW/S**

  **B=CarL/S**


  
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/b7f0be19-999a-4fde-bdcf-2cbcd5675a63)

### Some of the pictures are actually

![Userm3](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/e086161b-c0b5-40eb-b59a-263f7b17028e)

**step1**
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/54526e18-09d3-420c-a758-203fed34f305)

**step2**

![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/b75a4ece-6c34-408f-8797-5ffccb948992)

**step3**

![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/3586da7f-1901-4afc-9377-cb3e69dafccb)

**step4**

![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/486985f7-4292-4134-b309-176af1a84362)


## NODE-RED
Node Red Design
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/f8872570-cfd2-4133-a654-ae0f6080cf19)

Node Red interface
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/86bcc0e5-feb1-413d-b971-391c4d03a44d)





## Circuit Details

### Requirements
- Arduino(any model, even nano works)
 - ESP or any other Arduino compatible board to provide internet
- Ultrasonic Sensor(hc-sr04 or any)
- Arduino motor shield
- 4 DC Motors and wheels
- Basic car chassis
- Battery 



### Circuit Diagram
![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/2225861e-ab13-413b-a133-dd71e9003dc8)

## Steps to use the code
1. Download the file
2. Open Arduino IDE and select the port
3. Compile and Upload the file



## Prototype

![image](https://github.com/ENG-Rakan-Almutairi/-IOT-Based-Smart-Moving-Things-base/assets/170817969/108b2617-9512-4f93-9cb5-36cfc7cf03bc)

