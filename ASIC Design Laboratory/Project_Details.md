<h1>Final Project Details</h1>

The goal of this project was less about understanding how this design was used within a computer, but rather being able to put a complex system together in SystemVerilog. Prior to this point in this class, we did not have to work with any major integration challenges. Each lab was unique from the others, which gave us a fresh start each week. However, for this lab, each person worked on their own part, which then prompted collaboration with other group members to ensure timing and connectivity were correct. 

<h2>My contribution</h2>

<img width="1442" height="1680" alt="CDL_AHB_RTL_337 drawio" src="https://github.com/user-attachments/assets/75a8d2ed-2533-42fc-9e73-852c8b125def" />

The purpose of my section (shown above) was to communicate with the bus model, which would then communicate with the computer system. The top half of the design showcases the receiving end, which would take data into the system. As a part of the reading side, we can specify which port to read from as well as the size of data to read. The lower half of the design shows the sending side of the system, which would transmit data to the USB port. This part of the design can also be modulated to send different signals as well as different sizes of data. 

<h3>Challenges & obstacles</h3>

As mentioned earlier, one of the greatest challenges we faced during the design and testing process was integration between modules. We ultimately spent a large amount of time using QuestaSim waveforms to debug this process and find the result we were looking for. We would connect two parts together and test their functionality one piece at a time. When we spotted an issue, we would address the timing by adding a flip-flop, a piece of hardware used to delay a signal. We also relied heavily on the idea of "handshaking," which boils down to both systems acknowledging each other before any data is transferred. This was important because it ensured one side of the handshake was not unprepared, which avoided false transfers. 

While the concepts in this project are not the most complex, it was a great way to ensure my SystemVerilog skills were sufficient for future challenges! Without this project, I would not have been able to complete the challenges facing me in future semesters.  
