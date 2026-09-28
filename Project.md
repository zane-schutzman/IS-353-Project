IS355 Networking and Cyber Security
Group Members
Student Name	Student ID	Student Email
Zane Schutzman	1924285	zwschutzman@loyola.edu
Owen Steinetz	1928302	omsteinetz@loyola.edu
Gbemiro Omokayode	1904384	gdomokayode@loyola.edu
Charlie DiNapoli	1906216	cjdinapoli@loyola.edu
Communication Plan
We will use an iMessage group chat, which we have already created, to communicate throughout the project.

We will communicate every week to discuss what we have completed, what still needs to be done, and what we will work on next.

We will aim to complete one or two tasks each week.

Tasks
Form project group and create GitHub repository — [Name]

Create project plan and communication schedule — [Name]

Identify assumptions and requirements — [Name]

Design the network — [Name]

Create network diagram — [Name]

Develop IP addressing plan — [Name]

Recommend network hardware — [Name]

Research cloud providers — [Name]

Complete cloud service pricing comparison — [Name]

Compare backup strategies — [Name]

Conduct cyber security risk assessment — [Name]

Recommend security controls — [Name]

Review and improve network design — [Name]

Complete final report — [Name]

Prepare final submission — [Name]

Project Timeline
Week 4
form group
create GitHub repository
create project plan
Week 5
assumptions
requirements
begin network design
Week 6
network design
IP addressing
Week 7
network diagram
hardware recommendations
Week 8
upload draft network design to GitHub
Week 9
cloud provider research
pricing

## Assumptions and Requirements

### Requirements

- The company has two attached buildings: a factory and an office building.
- The factory normally has 20 to 25 workers.
- The office normally has 30 to 40 staff.
- The factory contains network-controlled machinery and conveyor belts.
- Factory machinery can use wired LAN or wireless Wi-Fi connections.
- Factory computers monitor and control the machinery.
- Office and factory users have both wired and wireless devices.
- The company has general-purpose office printers.
- The company has specialized printers, including large engineering printers and 3D printers.
- The company will use IP-based security cameras throughout the buildings.
- Security cameras will send video to a local server in the office.
- The company will use some cloud services, including a public website and email.
- Important information such as engineering designs and financial information will remain on local office servers.
- The network must contain at least three IP subnets: factory, office, and security cameras.
- Only /24 and /16 network masks may be used.
- Every IP address used in the network design must begin with the last two digits of one of the group members' student IDs.

- ### Assumptions

- The company will have one primary internet connection.
- A firewall will be placed between the company's internal network and the internet.
- Managed network switches will be used to support network segmentation.
- Separate networks will be used for factory devices, office devices, security cameras, and other specialized devices where appropriate.
- Wireless access points will be used to provide Wi-Fi throughout the office and factory.
- Guest wireless devices will be separated from the company's internal networks.
- The company will use local servers for important engineering and financial information.
- A local server will be used to store security camera footage.
- Network equipment and servers will be located in secure areas with restricted physical access.
- The network will use security controls such as firewalls, network segmentation, access controls, and regular backups.

- ## Network Design

### IP Addressing

The network will be divided into six separate /24 subnets. Network segmentation will separate factory equipment, office devices, security cameras, guest devices, servers, and network management traffic.

| Network | IP Address Range | Purpose |
|---|---|---|
| Factory | 85.10.0.0/24 | Factory machinery, conveyor belts, and factory computers |
| Office | 85.20.0.0/24 | Office computers, laptops, and printers |
| Security Cameras | 85.30.0.0/24 | IP security cameras |
| Guest Wi-Fi | 85.40.0.0/24 | Guest wireless devices |
| Servers | 85.50.0.0/24 | Local company servers |
| Network Management | 85.60.0.0/24 | Management of network equipment |
