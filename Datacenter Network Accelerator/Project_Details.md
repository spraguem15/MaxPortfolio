<h1>My contributions</h1>

As mentioned earlier, my contributions mainly relate to the base transport header (BTH). To provide further insight on this layer I will post a screenshot below that contains more precise information regarding this layer. 

<img width="1259" height="267" alt="image" src="https://github.com/user-attachments/assets/57a3ed8d-1b73-4ac4-87ce-a27e1309cb0e" />

<h2>Project background</h2>

This project is apart of my senior design project which spans from August 2025 to May 2026. This project is still currently in progress, with said progress ramping up in the spring of 2026. Much of our team's progress was hindered by our understanding of networks and their compatability with computers. As a result much of Fall 2025 semester was spent gaining background on networks with many of us taking a computer prototyping class (Computer Architecture & Design project). Some of the networks topics we covered relate to Packets & messages, TCP vs. UDP, RDMA, NICs and more. After building up our understanding of networks we used a scientific journal as a baseline for our project for reference. 

<h2>Current Progress</h2>

Much of the progress we have made has come in the form of planning and developing our understanding. We have also programmed all of our parts individually and are in the testing phasing before we begin integrating our project together. My contributions relates to programming the generating aspect of the BTH layer, which is highlighted below. 

<img width="1414" height="207" alt="image" src="https://github.com/user-attachments/assets/97220c66-39a0-4bdf-88c1-6e5bcf928fa2" />

Once our system has accessed the RDMA of the kernel/CPU we will have access to the information that was requested from the original sender. This information should now be put together as shown in the picture above. The majority of the fields shown there are pre-defined fields that are defaulted for the purpose of our design. However, as aforementioned there are two main areas that need to be determined (PSN & QPN). The generating side of things simply needs to communicate with the QP table and state table to determine this information which was assembled by a teammate. With this being said we spent a lot of time figuring out how these machines would work to avoid several problems, which will be discussed further below.

<h3>State table & QP table considerations</h3>

As you can see in the previous figure there are two different sides accessing the same machine (state table). During our research and design phase, this issue occured to be me prompting the question of how we will process both of these requests at the same time? In practice, our project would be sending and receiving messages at a constant rate, meaing we will be very busy. This creates an issue because we will be trying to 
