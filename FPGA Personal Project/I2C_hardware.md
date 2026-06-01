
<h1>Overview</h1>

For the sake of this project, I have created a slightly less operational version of the I2C communication protocol. Specifically for testing purposes, I have made it so that the temperature sensor device I am using will only be able to be read from. The sensor does offer capabilites to allow writing to it, however, I will not be using those as of now. After, I get the reading part working correctly, I will implement the rest of the features that create the standard I2C protocol. Additionally, the temperature sensor I am using has a smart start up feature, which essentially allows it to go right into reading mode. What this means for the software, is that we do not have to provide a specific address for "quick use", any address will automatically enable the quick read mode to be started. 

<h2>Top Level Diagram</h2>

Below is a diagram I am using to base my design off of. This design has not been integrating nicely into the I/O bus design, so there will need to be some adjustments made in order to better integrate everything. 

<img width="1217" height="508" alt="image" src="https://github.com/user-attachments/assets/76754b92-32c3-4b63-9d45-9584909669e6" />

The register module block essentially acts as a small set of regsiters, saving addresses and data that would be used during the design. This block is clocked at the overall FPGA speed of 100 Mhz, which is noteable since the finite state machine (FSM), is not. When metadata wants to be sent in, a start bit must be set high, this essentially acts as an enable signal for the register file, to tell it to store data. More research needs to be done on whether or not the I/O bus can provide this signal as well, maybe an entire 32 bit signal can be sent, which can then be segmented into different parts. 

After which we have the FSM itself. This is responsible for the sending & receiving of data between the master and slave. As of right now, data can only be read from the slave, meaning, you cannot send any data. This will be improved in the future. The FSM moves on the clock pulses of the SCL signal, which is a lower frequency version of clk, precisely 100 Khz. This speed is considered to be standard mode within I2C protocol, which is the reason why it was chosen. 

<img width="1222" height="745" alt="image" src="https://github.com/user-attachments/assets/7a0b010b-1991-4239-beb4-edacc5ebf314" />

The state machine above does raise some interesting questions. Bit level re-useability was not heavily considered when making this design, as it is simpler from a SystemVerilog perspective to simply make byte specific operations. However, I did think of the question whether this is faster and more area efficient than re-using states, but adding counters instead. The question rises of whether or not the area would increase more from increased states or additional counters. If things move accordingly, I would like to attempt to answer this question for myself, seeing whether or not 1 has a clear benefit than the other. Also given how small this hardware is in general, it may not matter at all. 

<h2>Verification</h2>

When it comes to verifying everything done here, I decided to move with an interactive testbench, meaning I would do more than simply check the values at certain points to make sure they are right. I2C has very specific transisitons which dictate the operation/movement that is occuring. For example a start sequence needs to pull SCL high for several cycles, then pull SDA low while keeping SCL high. To ensure that my design will work when actually implemented I decided to create a design that would have it's own states as well. This will allow the testbench to essentially "interact" with the module to send data back and forth dynamically. There will be a custom FSM for the testbench which will verify the functionality of the RTL created. The testbench FSM will essentially do the opposite of what the previsouly displayed FSM does, which will better verify the timing of everything. 

