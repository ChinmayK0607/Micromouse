# Micromouse
This is the official repository for the Micromouse project at IvLabs, VNIT Nagpur

## Objectives
The objectives of the summer internship were to create a compact robot that could autonomously solve any given maze. 

## Methodology
In the initial first weeks, we worked on implementing the software algorithms. We tried a set of algorithms, namely

1.Wall Following

2.BFS

3.DFS

4.Flood Fill

Code for each of the above mentioned can be found in ```Algorithmic Implementations``` Folder.

After this, we built a maze using corrugated sheets and started working on the hardware parts inclulding sensor testing and assembly.
The detailed hardware breakdown is mentioned below. 

Initially we had thought about using PID for turning and other operations, but due to error buildup, 
we went with using sensor data for precise turning, at the end of it, we could achieve the objectives within stipulated time.
Testing included 5 different mazes.

Image of the final bot:




## Hardware Explanation
Here is a both high level and low level diagram for understanding of the hardware implementation
![image](https://github.com/ChinmayK0607/Micromouse/assets/114411195/6be8035b-0604-475b-956f-26d8a51b0aa2)

![image](https://github.com/ChinmayK0607/Micromouse/assets/114411195/b1fa66ec-f1b0-48fe-924e-58f44655b7bf)

The circuit overall is controlled by the Ardiuno nano. The code for movement and speed control as well for maintaining a particular distance form the wall is uploaded in the Ardiuno nano.
It analyses the data sent by the motor encoders and calulates the distance covered accordingly. 
It also reads the
data from all the three ultrasonic sensors and gives output to the motor so that the bot maintains a particular distance from the wall.

The motor driver recieves the input from the Ardiuno nano and accordingly supplies the signal to the motor so that the motor can perform the required movement.

The circuit drives it power from a 7.4V LiPo batttery.

The connections of the circuit are as shown in the circuit digram above.

Link to a detailed breakdown of hardware: https://hackmd.io/yFryJIJRRAq1Xr2IdxVAPA

## Software Explanation

Since the initial simulations were in python, we had to create data structures for the maze map and directions. We implemented flood fill as the final algorithm as it was the fastest comparitively and gave good results.

How it works:
The flood fill is an optimistic search algorithm that can help in solving mazes, it simulates water flooding a maze and reaching the goal and thus the name. 

It initially assumes that there are no walls and generates a first maze map using bfs/dfs. A maze map considers the goal as 0 and each preceding cell has value one more than the earlier cell.

Example : ``` current_cell.value() = previous_cell.value()+1 ; ```

Flood fill video:

![Untitled video - Made with Clipchamp (5)](https://github.com/ChinmayK0607/Micromouse/assets/114411195/2238fc76-befa-4fdc-a332-68aed780f492)




The mouse then runs once to generate a maze map according to intial run.
It then backtracks using a different path and then decides the shortest path based on these two runs.

Link to extensive breakdown of code: https://hackmd.io/@l_WDq7lkQq29Pz-KD1JPNA/HkYDExRTh


## How to run the code
Download the arudino ide and run the files.

For simulation:
``` pip install pyamaze```

Then you are good to go
