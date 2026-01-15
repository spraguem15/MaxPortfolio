<h1>Early design</h1>

Early on in this class we started with a simple design by working on a single cycle processor. This processor would ideally complete 1 instruction per clock cycle, ignoring any memory accessses. Although the design worked well, it was not optimized well leaving a lot of room for imporvement. Below is the RTL used for the single cycle design. 

<img width="1398" height="1044" alt="Lab4_Datapath drawio" src="https://github.com/user-attachments/assets/2db7c27c-b64f-44fa-b543-23a2c926c266" />


<h1>Pipeline & datapath improvements</h1>

After verifying our design worked at a basic level, we moved forward by optimizing our datapath through two main factors. First of which was pipelining our design, which would not improve our latency, but would greatly improve our throughput. In order to pipeline our design we took our original design and divided it into 5 main stages, fetch, decode, execute, memory and writeback. These stages are very common in computer architecture and have been around for a long time. The second optmization that was made was forwarding which involves moving data to different parts of our datapath based on current and prior use. To achieve this optmization we create a forwarding unit which would be responsible for selecting the appropriate data within the execution stage. Finally we added a hazard unit as well which was responsible for flushing and delaying different stages in our pipeline.

<img width="3374" height="1781" alt="Lab5_Datapath_Pipelined drawio (1)" src="https://github.com/user-attachments/assets/e76441e4-1c55-4e19-b930-3e30e4c57941" />
