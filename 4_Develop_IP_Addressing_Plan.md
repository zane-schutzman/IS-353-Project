# Develop IP Addressing Plan

## IP Addressing

The network will be divided into six separate `/24` subnets. Network segmentation will separate factory equipment, office devices, security cameras, guest devices, servers, and network management traffic.

| Network            | IP Address | Range | Purpose                                                  |
| ------------------ | -----------| ------| -------------------------------------------------------- |
| Factory            | 85.10.0.0  | /24   | Factory machinery, conveyor belts, and factory computers |
| Office             | 85.20.0.0  | /24   | Office computers, laptops, and printers                  |
| Security Cameras   | 85.30.0.0  | /24   | IP security cameras                                      |
| Guest Wi-Fi        | 85.40.0.0  | /24   | Guest wireless devices                                   |
| Servers            | 85.50.0.0  | /24   | Local company servers                                    |
| Network Management | 85.60.0.0  | /24   | Management of network equipment                          |

## IP Addressing Plan

All internal networks use a /24 subnet mask (255.255.255.0). The first octet of the IP addresses is 85, which corresponds to the last two digits of a group member's student ID.

| Device / Device Group | IP Address / Range | Network | Purpose |
|---|---|---|---|
| Factory Gateway | 85.10.0.1 | Factory | Default gateway for factory devices |
| Office Gateway | 85.20.0.1 | Office | Default gateway for office devices |
| Camera Gateway | 85.30.0.1 | Cameras | Default gateway for security cameras |
| Guest Gateway | 85.40.0.1 | Guest Wi-Fi | Default gateway for guest devices |
| Server Gateway | 85.50.0.1 | Servers | Default gateway for local servers |
| Management Gateway | 85.60.0.1 | Management | Default gateway for network equipment |
| Factory Switch | 85.60.0.2 | Management | Management address for factory switch |
| Office Switch | 85.60.0.3 | Management | Management address for office switch |
| Camera Switch | 85.60.0.4 | Management | Management address for camera switch |
| Server Switch | 85.60.0.5 | Management | Management address for server switch |
| Factory PCs | 85.10.0.10–85.10.0.34 | Factory | Factory employee computers |
| Office Computers | 85.20.0.10–85.20.0.49 | Office | Employee computers |
| IP Cameras | 85.30.0.10–85.30.0.59 | Cameras | Security cameras |
| Guest Devices | 85.40.0.10–85.40.0.99 | Guest Wi-Fi | Temporary/guest devices |
| File Server | 85.50.0.10 | Servers | Engineering and financial files |
| Camera Server | 85.50.0.11 | Servers | Stores security camera footage |

## Device IP Addresses

| Device | IP Address | Network |
|---|---|---|
| Firewall | 85.10.0.1 | Network Gateway |
| Core Switch | 85.60.0.1 | Management |
| Factory Switch | 85.60.0.2 | Management |
| Office Switch | 85.60.0.3 | Management |
| Camera Switch | 85.60.0.4 | Management |
| Server Switch | 85.60.0.5 | Management |
| Factory PCs | 85.10.0.10–85.10.0.34 | Factory |
| Office Computers | 85.20.0.10–85.20.0.49 | Office |
| IP Cameras | 85.30.0.10–85.30.0.59 | Cameras |
| Guest Devices | 85.40.0.10–85.40.0.99 | Guest |
| File Server | 85.50.0.10 | Servers |
| Camera Server | 85.50.0.11 | Servers |
