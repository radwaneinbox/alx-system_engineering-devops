# Postmortem Report: The Great Web Service Slowdown of August 2024

Welcome to our riveting postmortem on the web service slowdown that had us all on the edge of our seats. Grab your popcorn as we unravel the mystery of what went wrong, what we learned, and how we’ll prevent it from happening again!

## 🎯 Issue Summary

- **⏰ Duration:** August 12, 2024, 15:30 UTC - August 12, 2024, 18:15 UTC
- **⚠️ Impact:** Our web application decided to take a nap, causing severe slowdowns and intermittent failures for about 60% of our users. Error rates spiked, and frustration levels soared.
- **🔍 Root Cause:** A misconfigured load balancer’s SSL termination settings led to a traffic jam that overwhelmed our application servers.

## 📅 Timeline

- **15:30 UTC:** The monitoring system sounded the alarm with high response times and a surge in 5xx errors. Time to investigate!
- **15:35 UTC:** The on-call engineer confirmed the issue and began troubleshooting. Coffee break postponed.
- **15:45 UTC:** Initial investigation focused on the usual suspects: application servers and databases. No issues found—mystery deepens.
- **16:00 UTC:** Customers started complaining. Looks like their patience was running thin.
- **16:15 UTC:** We chased wild geese—DNS and firewall settings—all checked out fine.
- **16:45 UTC:** Escalation to the Network Engineering team. They dug deeper and found the real culprit.
- **17:00 UTC:** Discovered that the load balancer’s SSL termination settings were misconfigured. It was like trying to drive a car with the brakes on.
- **17:15 UTC:** Fixed the settings. Traffic started flowing smoothly again, and service was restored.
- **18:15 UTC:** All systems back to normal. Monitoring confirmed everything was running smoothly.

## 🔧 Root Cause and Resolution

- **Root Cause:** The load balancer's SSL termination settings were set up incorrectly, creating a traffic bottleneck. Our application servers were swamped with more traffic than they could handle.
- **Resolution:** Corrected the SSL termination settings on the load balancer, allowing it to handle HTTPS traffic properly. The application servers could breathe easy once more.

## 🛠️ Corrective and Preventative Measures

- **Improvements/Fixes:**
  - **Pre-Deployment Testing:** Ensure SSL settings are thoroughly tested before going live. It’s like having a dress rehearsal to avoid last-minute surprises.
  - **Enhanced Monitoring:** Upgrade our monitoring system to detect load balancer configuration issues early.
  - **Automated Checks:** Implement automated checks to spot misconfigurations before they impact production.

- **Tasks to Address the Issue:**
  - Review and verify SSL termination settings based on best practices.
  - Add specific monitoring alerts for load balancer traffic patterns.
  - Develop a comprehensive deployment checklist for load balancer configurations.
  - Conduct post-deployment reviews for major changes in network or server settings.

## 📈 Diagram: The SSL Termination Tango

![SSL Termination Tango](https://example.com/ssl-termination-tango.png)  
*An illustrative dance of our load balancer’s settings before and after the fix.*

## 🗂️ Repository Details

- **GitHub repository:** [alx-system_engineering-devops](https://github.com/alx-system-engineering-devops)
- **Directory:** 0x19-postmortem
- **File:** [README.md](https://github.com/alx-system-engineering-devops/0x19-postmortem/README.md)

## 🚀 Final Note

Every challenge is a chance to improve. Thanks for sticking with us through this journey. Stay tuned for more updates and tech insights!


