# Event Driven Automation with F5 and Ansible

## About

This repository contains the code for a demonstration ([YouTube Video](https://www.youtube.com/watch?v=V676EF_bq-4)) of how to use F5 BIG-IP with Event Driven Ansible and Ansible Automation Platform to create Event Driven Security.

The lab was set up with the following components:

* F5 BIG-IP frontending an application (DVWA) with an AWAF Security Policy in place and running, forwarding syslogs, and monitoring logs to ElasticSearch.
* ElasticSearch and Kibana as our monitoring and event triggering tool (via Watchers - using [watch_blocked_ips.json](https://github.com/f5devcentral/f5-bd-ansible-eda-demo/blob/main/elastic/watch_blocked_ips.json)).
* Event Driven Ansible to receive triggered events from ElasticSearch Watchers and passing the payloads from those triggered events into Ansible Automation Platform (using [webhook-block-ips.yaml](https://github.com/f5devcentral/f5-bd-ansible-eda-demo/blob/main/rulebooks/webhook-block-ips.yaml)).
* Ansible Automation Platform to run a template pre-setup for blocking IP addresses (utilizing the payload from Event Driven Ansible to modify the WAF policy on the F5 BIG-IP - [block-ips.yaml](https://github.com/f5devcentral/f5-bd-ansible-eda-demo/blob/main/playbooks/block-ips.yaml)).

By doing this, our solution is Full Circle, meaning we start from the F5 BIG-IP and end at the F5 BIG-IP!

## Requirements for Event Driven Automation with F5 and Ansible

1. **F5 BIG-IP:**
   - Hardware or virtual appliance capable of running BIG-IP software.
   - Licensing for Advanced Web Application Firewall (AWAF) functionality, if applicable.

2. **Ansible Automation Platform and Event Driven Ansible:**
   - Installation of Ansible Automation Platform with Event Driven Ansible.
   - Access to Ansible playbooks/rulebooks for automation tasks (This Git Repo).
   - Integration with Event Driven Ansible for event handling.

3. **ElasticSearch and Kibana:**
   - Deployment of ElasticSearch and Kibana for log storage, monitoring, and event triggering.
   - Configuration of Watchers in ElasticSearch for event detection and triggering.

4. **DVWA (Damn Vulnerable Web Application):**
   - Deployment of DVWA or similar web application for testing and demonstration purposes.
   - Configuration of F5 BIG-IP to front-end DVWA.

5. **Integration Components:**
   - Integration between F5 BIG-IP and ElasticSearch/Kibana for forwarding syslogs and monitoring logs.
   - Configuration of Event Driven Ansible to receive triggered events from ElasticSearch Watchers.
   - Predefined Ansible playbooks or roles for specific automation tasks (e.g., blocking IP addresses on F5 BIG-IP) (This Git Repo).

6. **Networking Setup:**
   - Proper networking setup to ensure communication between all components.
   - Configuration of network policies, routing, and firewall rules as needed.

## Common Use Cases for Event Driven Automation with F5 and Ansible

1. **Automated Security Response:**
   - Utilize F5 BIG-IP, Ansible Automation Platform, and ElasticSearch/Kibana to automate security response processes.
   - Example: Detect suspicious activities or attacks on web applications (such as DVWA), trigger alerts through ElasticSearch Watchers, and automatically block malicious IP addresses on the F5 BIG-IP's AWAF Security Policy using Ansible Automation Platform.

2. **Dynamic Policy Enforcement:**
   - Use Event Driven Ansible to dynamically enforce security policies based on real-time events.
   - Example: Modify WAF (Web Application Firewall) policies on the F5 BIG-IP based on threat intelligence or specific triggers detected in the logs forwarded to ElasticSearch.

3. **Continuous Monitoring and Remediation:**
   - Implement continuous monitoring of application traffic and security events through ElasticSearch and Kibana.
   - Automatically execute predefined Ansible playbooks (such as blocking IP addresses) to remediate issues detected in the monitoring process.
   
4. **Integration with Existing Tools:**
   - Facilitate integration with existing tools and platforms using Ansible's capabilities.
   - Example: Orchestrate actions across different parts of the infrastructure by leveraging Ansible's integration with various systems and tools.

5. **Full Circle Automation:**
   - Highlight the end-to-end automation capability of the solution.
   - Example: Start from the F5 BIG-IP as the entry point for traffic, go through monitoring and detection with ElasticSearch/Kibana, handle events and orchestrate actions with Event Driven Ansible, and finally, make adjustments on the F5 BIG-IP to mitigate risks or threats, forming a closed-loop automation workflow.


# Related Information

* [YouTube Video on Proactive Event Driven Security](https://www.youtube.com/watch?v=V676EF_bq-4)
* [GitHub Repository for the code](https://github.com/f5devcentral/f5-bd-ansible-eda-demo)
* **Currently being Repaired** - [F5 Devcentral Article on The solutions](https://community.f5.com/t5/technical-articles/security-automation-with-f5-big-ip-and-event-driven-ansible/ta-p/315242?emcs_t=S2h8ZW1haWx8dG9waWNfc3Vic2NyaXB0aW9ufExRR1UwTFhVMkxLUE84fDMxNTI0MnxTVUJTQ1JJUFRJT05TfGhL)

# License Information

The code is free-to-use for anyone who wants it.
