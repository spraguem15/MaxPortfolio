
<h1>Overview</h1>

For the sake of this project, I have created a slightly less operational version of the I2C communication protocol. Specifically for testing purposes, I have made it so that the temperature sensor device I am using will only be able to be read from. The sensor does offer capabilites to allow writing to it, however, I will not be using those as of now. After, I get the reading part working correctly, I will implement the rest of the features that create the standard I2C protocol. Additionally, the temperature sensor I am using has a smart start up feature, which essentially allows it to go right into reading mode. What this means for the software, is that we do not have to provide a specific address for "quick use", any address will automatically enable the quick read mode to be started. 

<h2>Top Level Diagram</h2>

Below is a diagram I am using to base my design off of. This design has not been integrating nicely into the I/O bus design, so there will need to be some adjustments made in order to better integrate everything. 

<img width="1265" height="597" alt="image" src="https://github.com/user-attachments/assets/c15ce2d5-9129-4ced-9afe-dd19a11be6f5" />

