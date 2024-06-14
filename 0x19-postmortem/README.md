Postmortem: Website Outage on June 10, 2024
Issue Summary
Duration: June 10, 2024, from 14:30 to 16:00 UTC

Impact: The main e-commerce website was down, preventing all users from accessing the site. Approximately 100% of users were affected, resulting in a significant drop in sales and user frustration.

Root Cause: The root cause was a misconfiguration in the load balancer settings during a routine update, which led to a failure in routing traffic to the web servers.

Timeline
14:30 UTC: Issue detected by monitoring alert indicating a sudden drop in web traffic.
14:32 UTC: Engineers confirmed the outage by attempting to access the website.
14:35 UTC: Initial investigation started focusing on the web servers, assuming a server crash.
14:45 UTC: Misleading path: Checked database connections and server logs, found no anomalies.
15:00 UTC: Issue escalated to the network team after web server issues were ruled out.
15:15 UTC: Network team identified a misconfiguration in the load balancer settings.
15:30 UTC: Load balancer settings were corrected.
15:45 UTC: System functionality tested and verified.
16:00 UTC: Website fully operational and accessible to all users.
Root Cause and Resolution
Root Cause:
The outage was caused by an incorrect configuration in the load balancer. During a scheduled update, a setting was inadvertently changed, which caused the load balancer to fail in routing traffic to the web servers. This resulted in the website being inaccessible to users.

Resolution:
The network team identified the incorrect setting in the load balancer configuration. They reverted the setting to its previous state and thoroughly tested the configuration to ensure that the traffic was correctly routed. After confirming that the website was fully operational, the team monitored the system closely for the next hour to ensure stability.

Corrective and Preventative Measures
Improvements:

Enhance the update procedure to include a thorough review of changes, especially in critical components like load balancers.
Implement additional monitoring and alerts specific to load balancer configurations to detect misconfigurations more quickly.
Improve communication and escalation processes to ensure quicker involvement of the network team in similar incidents.
Tasks:

Update Procedures:
Review and update the standard operating procedures (SOP) for load balancer updates.
Add a mandatory peer review step for configuration changes.
Monitoring and Alerts:
Configure detailed monitoring on the load balancer to detect configuration changes.
Implement alerts for unusual traffic patterns or drops in traffic at the load balancer level.
Communication and Training:
Conduct a training session for the engineering and network teams on the new procedures and monitoring tools.
Create a quick-reference guide for troubleshooting load balancer issues.
Documentation:
Document the incident in detail, including the root cause, resolution steps, and preventive measures.
Regularly update the incident management documentation based on lessons learned from outages.
By implementing these measures, we aim to prevent similar outages in the future and ensure a more resilient and reliable service for our users.
