# Design the Network

## Network Design Decisions

The network is divided into separate subnets to improve organization, security, and network management. The factory, office, security cameras, guest Wi-Fi, servers, and network management equipment each have their own subnet.

The factory network is separated from the office network because it contains network-controlled machinery and conveyor belts. This helps limit unnecessary traffic between factory equipment and office devices.

The security camera network is separate from the other networks so that camera traffic does not interfere with normal business traffic. The cameras connect to a dedicated camera switch and send their footage to the local camera server.

The guest Wi-Fi network is separated from the company's internal networks. Guest devices should not have direct access to company computers, servers, machinery, or security cameras.

The server network contains the local file server and camera server. The file server stores important engineering and financial information, while the camera server stores security camera footage.

A separate management network is used for managing switches and other network equipment. This keeps management traffic separate from normal user traffic.

The firewall is placed between the internet and the internal network. It provides traffic filtering and helps protect the company's internal systems from unauthorized internet traffic.
