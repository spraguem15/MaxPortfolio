<img width="541" height="699" alt="image" src="https://github.com/user-attachments/assets/214406cc-2957-4b1b-bf5d-990633e8ffa7" />
<h6>The following image was not created by me, but another group depicting our project from a top view</h6>

<h1>Project Overview</h1>

Currently I am working with a group called SoCET (System on Chip Extension Technology) within the DNA (Datacenter Network Accelerator) subteam. The problem we are trying to solve relates to datacenters and how they transmit data between computers. Each computer has to properly package all relevant information before it can be sent out to another computer. The problem with this is that a lot of time is spent on packaging this data which leaves performance on the table to perform other tasks. Our solution comes into play by essentially creating a smart NIC (network interface card) that reduces the workload for the CPU by offloading the work to an FPGA. This FPGA will take in the data from the CPU and package it appropriately so it can be passed along to the destination. 

<h2>My contribution</h2>

My contribution to this project relates to a specific layer that needs to be formatted properly so it can be sent out. Our project follows the IP version four (IPV4) standard of communication which contains a variety of different headers, one of those being the base transport header (BTH). This header is responsible for two main things, keeping track of the queue pair number (QPN) and the packet sequence number (PSN). The QPN is responsible for keeping track of who is talking with who. The PSN keeps order for all the packets of data being sent out, to ensure everything is sent/recieved in the proper order. The team I worked with was responsible for designing, developing and testing a system that would reliability organize the BTH layer. The "Project Details" page will detail more information on this project and the progress made. 
