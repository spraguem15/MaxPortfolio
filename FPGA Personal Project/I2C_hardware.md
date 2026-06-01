
<h1>Overview</h1>

For the sake of this project, I have created a slightly less operational version of the I2C communication protocol. Specifically for testing purposes, I have made it so that the temperature sensor device I am using will only be able to be read from. The sensor does offer capabilites to allow writing to it, however, I will not be using those as of now. After, I get the reading part working correctly, I will implement the rest of the features that create the standard I2C protocol. Additionally, the temperature sensor I am using has a smart start up feature, which essentially allows it to go right into reading mode. What this means for the software, is that we do not have to provide a specific address for "quick use", any address will automatically enable the quick read mode to be started. 

<h2>Top Level Diagram</h2>

Below is a diagram I am using to base my design off of. This design has not been integrating nicely into the I/O bus design, so there will need to be some adjustments made in order to better integrate everything. 

<img width="1217" height="508" alt="image" src="https://github.com/user-attachments/assets/76754b92-32c3-4b63-9d45-9584909669e6" />

The register module block essentially acts as a small set of regsiters, saving addresses and data that would be used during the design. This block is clocked at the overall FPGA speed of 100 Mhz, which is noteable since the finite state machine (FSM), is not. When metadata wants to be sent in, a start bit must be set high, this essentially acts as an enable signal for the register file, to tell it to store data. More research needs to be done on whether or not the I/O bus can provide this signal as well, maybe an entire 32 bit signal can be sent, which can then be segmented into different parts. 
