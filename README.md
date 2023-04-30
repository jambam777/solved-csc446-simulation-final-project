Download Link: https://assignmentchef.com/product/solved-csc446-simulation-final-project
<br>
Regarding the course project, I prefer that you could come out of some project topics that you feel are interesting and suitable for simulation study. The simulation project could be in any application domain, such as simulation of hospital emergency, simulation of service requests to data centers, simulation of the charging/discharging of electrical vehicles, simulation of vehicle traffic in a city, and so on. Please send me your proposed topic, if any, by Nov. 5.




If you do not have anything in mind, the following is a project topic that you can work on.

===========================

Project: Priority Queueing to Alleviate Packet Re-ordering Problem




Background: In the Internet, data packets from a source node (e.g., a web server) to a destination (e.g., a client computer) may experience different delay, resulting in out-oforder packet arrivals at the destination. A common solution is to buffer out-of-order packets at the destination and re-order the packets into correct order before sending them to the application layer. This project is to investigate the benefit of using priority queueing in the intermediate routers to alleviate the packet re-ordering problem.




Simulation Setup: We assume that the network includes a source node, a router, and a destination. Data packets are transmitted from the source to the router and then to the destination. The source node generates Poisson traffic, with average rate of 20 packets per second. The transmission speed of the source node is 10 Mbps. Each packet has a

unique sequence number and all data packets have the fixed length of 1000 Bytes (1 Byte = 8 bits). From the source to the router, packets experience a random delay which follows a normal distribution with the mean of <strong><em>x</em> </strong>seconds and the standard deviation of <strong><em>y</em></strong> seconds. From the router to the destination, packets experience a fixed delay of 50 ms.




The router has two queues, one having a higher priority than the other. It also keeps track the largest sequence number it has seen so far, called <em>currentSeq</em>. If the sequence number of the incoming packet is larger than <em>currentSeq</em>, we call the incoming packet an in-order packet and update the <em>currentSeq</em> as the same as the sequence number of the incoming packet. Otherwise, the incoming packet is considered out-of-order. When a packet arrives, if the router is idle, the router transmits the packet immediately. Otherwise, the packet will be put into the low priority queue if it is an in-order packet and will be put into the high priority queue if it is an out-of-order packet. We assume non-preemptive scheduling (i.e., when the router starts transmission a lower-priority packet, the transmission cannot be interrupted even if a higher-priority packet arrivals.) and work conserving (i.e., the router cannot be idle if there are packets waiting in the queues). Nevertheless, when the router finishes transmission of a packet, it always serves the high priority queue first if there are packets in that queue. The transmission speed of the router is 15 Mbps.




Set the sizes of both queues in the router as 10M Bytes. When an incoming packet finds its corresponding queue is full, the incoming packet will be dropped.







Requirement: Simulate the above Priority Queueing model. You can re-use and modify the sample code provided in Assignment 1. The following performance metrics should be evaluated:

<ul>

 <li>Packet out-of-order rate: It is defined as the ratio of the total number of out-of-order packets over the total number of packets.</li>

 <li>Average packet delay: It is defined as sum of the end-to-end delay of all packets divided by the total number of packets.</li>

 <li>Average packet loss rate: It is defined as the ratio of total number of packets dropped by the router over the total number of packets.</li>

 <li>Compare the results if the router is modelled as a single FIFO queue, single server system. What is your conclusion?</li>

</ul>













<h1>Quick Guideline for Running Simulation</h1>

<strong> </strong>

Make sure you run the simulations long enough producing enough data • Run the simulations with different combinations of x and y values.

<ul>

 <li>For each combination (scenario), run the simulations with at least five different seeds</li>

 <li>For each run, collect the stats (e.g., the packet out-of-order rate and average packet delay if your project is to study the benefit of using priority Queueing to solve packet re-ordering problem)</li>

 <li>Compute confidence intervals for each of the metrics, with confidence level set as 95%.</li>

</ul>




<h1>Quick Guideline for Writing Report</h1>




Write the report in the following format:

–Brief problem (Project) Description

–The simulation model (e.g., the problem mapping to an equivalent priority queueing model)

–Simulation goals and Simulation parameters –Methodology:

<ul>

 <li>How is your simulation built? (e.g., why is your simulator valid for the simulation model?)</li>

 <li>How did you setup the simulations?</li>

 <li>How did you collect the stats? –Analysis</li>

 <li>For each run, report the collected statistics</li>

 <li>For each scenario, find the average stats across five different runs using different initial seeds</li>

</ul>

–Conclusion: What conclusion can be drawn from your simulation study with respect to the problem under investigation?











