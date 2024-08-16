  Postmortem: Outage Incident on Web-  Application


 Issue Summary: Duration: June, 15th 2024, 8.00 AM — June,17th, 2024, 12:30pm (WAT) 
Impact: The web application experienced intermittent downtime, 
resulting in slow response times and partial service disruption. 
Approximately 40% of users were affected during this period.


Timeline:
- June,15th, 2024, 8:30am (WAT): The issue was detected 
when monitoring alerts indicated a significant increase in response time.

- The engineering team immediately started investigating the issue, 
suspecting a potential database problem.


- Misleadingly, the investigation initially focused on the database 
cluster due to a recent deployment that involved schema changes.


- The incident was escalated to the database administration team to assess the potential 
impact of the schema changes on the cluster’s performance.


- Further investigation revealed no abnormalities within the database cluster, 
prompting the team to explore other areas of the system.


- June 17th, 2024, 12:30pm (WAT): The root cause was identified as an overloaded cache layer, 
leading to increased latency and intermittent failures.

- The incident was escalated to the infrastructure team for immediate resolution.
June 17th, 2024, 12:30pm (WAT): The incident was resolved, and the web application’s performance returned to normal.


Root Cause and Resolution: The root cause of the issue was an overloaded cache layer. 
The increased load on the system caused the cache to evict frequently accessed data, 
resulting in higher latency and intermittent failures. The cache’s eviction 
policy was not adequately configured to handle the sudden surge in traffic.


To resolve the issue, the infrastructure team adjusted the cache configuration by 
increasing its capacity and optimizing the eviction policy. Additionally, 
they implemented a monitoring system to provide early warnings when the cache utilization reaches critical levels. 
These measures aimed to prevent similar cache overload situations in the future.


Corrective and Preventative Measures: To improve the overall system stability, several actions will be taken:


Optimize cache eviction policies: Review and fine-tune the cache eviction 
policies based on usage patterns and anticipated traffic fluctuations.


Scale cache infrastructure: Evaluate the current cache infrastructure and determine if additional resources or 
