
<h1>Project Overview</h1>

The goal of this project was to combine several of the different concepts I have learned over the course of my career, so that I can build hands on experience integrating these systems. I choose to do this on an FPGA, because it will allow me to create custom hardware, implement embedded software and build the bridge between software and hardware. Overall I am hoping to learn some new things from this project as well as refresh myself on previous skills I learned from University. 

<h2>Project Specifics</h2>

The FPGA board I will be using for this project will be the _Digilent Arty S7-50_, which utilizes the _Xilinx Spartan-7 FPGA_. The reason behind choosing this board was that it was easily attainable and it uses industry level equipment. In order to actually create the project I will be using _Vivado_ and _Vitis_ to integrate everything. While I have created my own CPU before, I will be using the openly avaiable MicroBlaze processor, which is readily available to be put onto FPGAs and used with ease. 

In regard to what this project will actually do, I want the FPGA board to communicate with another device/sensor, through a standard communication protocol. That information will then be manipulated and moved by the CPU to a Display of some sort which will provide a formatted version of what is going on. 

For the sensor I will be using the PmodTMP2, a temperature sensor that uses I2C communication. In order to actually use I2C I will be created the hardware myself in SystemVerilog in Vivado. Once I have created and verified the hardware for the I2C protocol, I will use the microblaze CPU to request the information from the sensor and I will use it to convert the raw data into useable temperature readings. After which I will then send the data out to a display of some sort (TBD), which will give a live temperature reading from the sensor. If applicable, I would also like to add some sort of graphic accelerator, which would allow me to create a more detailed, vibrant display at a more efficient rate, given that CPUs struggle with this task. It will also be a good, practical experience creating a fake "GPU" that interface with the surrounding system. Below is a diagram that shows the entire system and how everything interacts with one another. 

<img width="826" height="653" alt="image" src="https://github.com/user-attachments/assets/6d3533e6-6ec1-4561-a140-cbf96bf88fc9" />

In my background I have a lot of experience in how the CPU operates, however, I have not worked with creating and managing hardware that operates with I/O. I am hoping to learn more about the fundamentals of how the I/O Bus works, in conjunction to topics like memory mapped addresses. Once I have learned an adequate amount of information, I will update all diagrams to reflect the most accurate information as possible. 
