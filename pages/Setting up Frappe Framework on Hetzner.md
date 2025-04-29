- Use Cloudi and click new project (project name- setting up frappe framework on hetzner)and add github from frappe and add all things without exiding too much %
  logseq.order-list-type:: number
- we addedd frappe/frappe and frappe/press
- set new instruction for example "Help me setting up press on Hetzner"
- and ask with something like "Help me set uppress on cloud on Hetzner"
- How many servers needed
- Ok give me datails guide and steps to setup and connect each server..i have three of em
- how to setup the domain, my dmain is logicna-podloga.com, i am using cloud flare
-
- 2.Setting Up Press with Your Domain on Cloudflare
	- for our domain for example idk logicna-podloga.com using cloudflare as dns provider.
	- We need to have 3 servers set up on hetzner
	- ## Domain and Subdomain Structure
	  
	  For a Press installation, you'll need to create several subdomains:
	- **Press Dashboard**: `press.logicna-podloga.com` (main interface)
	- **Proxy Server**: `proxy.logicna-podloga.com`
	- **Database Server**: `db.logicna-podloga.com`
	- **Wildcard Domain**: `*.logicna-podloga.com` (for dynamically created sites)
	- Cloudflare DNS Configuration
	- Add DNS Records
	- Cloudflare SSL/TLS Settings
	-
	- # For each Server before we go for Press server setup commands, we need to go into that server on terminal with ssh root@Server-IP (add ip of corespoding server). After finishing all setup for each server...exit all the way needed and enter another server and again setup all comands
		- # Press Server Setup Commands
		- ## Initial Setup
		- These steps needed for all thes ervers...steps mostly the same
		- Ask sonet if confused
	-
		- # Proxy Server Setup Commands
		- ## Initial Setup
	-
		- # Database Server Setup Commands
		- ## Initial Setup
	-
		- # Cloudflare DNS Setup for Press
		  
		  This guide explains how to configure Cloudflare DNS for your Press installation with `logicna-podloga.com` domain.
	-
	-