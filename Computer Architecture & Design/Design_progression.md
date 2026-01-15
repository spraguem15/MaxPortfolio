<h1>Early design</h1>

Early on in this class, we started with a simple design by working on a single-cycle processor. This processor would ideally complete 1 instruction per clock cycle, ignoring any memory accesses. Although the design worked well, it was not optimized, leaving a lot of room for improvement. Below is the RTL diagram used for the single-cycle design. 

<img width="1398" height="1044" alt="Lab4_Datapath drawio" src="https://github.com/user-attachments/assets/2db7c27c-b64f-44fa-b543-23a2c926c266" />


<h1>Pipeline & datapath improvements</h1>

After verifying our design worked at a basic level, we moved forward by optimizing our datapath through two main factors. The first of which was pipelining our design, which would not improve our latency, but would greatly improve our throughput. In order to pipeline our design, we took our original design and divided it into five main stages: fetch, decode, execute, memory, and writeback. These stages are very common in computer architecture and have been around for a long time. The second optimization that was made was forwarding, which involves moving data to different parts of our datapath based on current and prior use. To achieve this optimization, we created a forwarding unit which would be responsible for selecting the appropriate data within the execution stage. Finally, we added a hazard unit as well, which was responsible for flushing and delaying different stages in our pipeline.

<img width="3374" height="1781" alt="Lab5_Datapath_Pipelined drawio (1)" src="https://github.com/user-attachments/assets/e76441e4-1c55-4e19-b930-3e30e4c57941" />


<h1>Cache considerations</h1>

The biggest cost to performance that we faced with our design was accessing memory. In our system, memory accesses took several cycles, but in reality they can take tens of cycles to be completed. In order to address this issue, we created two caches below the datapath: one storing recent instructions and one storing recent data accesses. In many different programs, there are large chunks of repeating code. Instead of performing repetitive accesses to memory and wasting many cycles, we can store the values in a cache that will have a hit time of 1 cycle, greatly reducing the number of cycles needed to access memory. The following RTL shows the RTL diagram for the data cache we implemented. 

<img width="1360" height="610" alt="Cache RTLs-Dcache drawio" src="https://github.com/user-attachments/assets/0649d5e7-ff2d-4990-9cb0-c042b79c7b72" />

<h1>Dual Core Introduction</h1>

After adding our caches, we moved on to our final optimization of adding a second core to our design. This introduced two new challenges that needed to be addressed because of the second core. The first of which was making sure each data cache had the most up-to-date values and status for the frames within. The second challenge was making sure the design was synchronized, meaning a global variable could be updated one at a time without error. The solution to this issue was the introduction of a bus controller, which would arbitrate access to memory between the two cores as well as introduce snooping between both. This solution is effective for two cores, as issues like snooping are relatively simple; however, if we were to add more cores, we would have needed a different solution. Below is an RTL diagram of our bus controller.

<img width="956" height="683" alt="Bus_controller_437-Top Level drawio" src="https://github.com/user-attachments/assets/5f19537e-bf31-450f-a86e-caa2aecfafc8" />
