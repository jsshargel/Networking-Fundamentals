# Networking-Fundamentals
This information is here for me to learn networking fundamentals and as a source to come back to when needed. This information is from the Networking Fundamentals playlist under the Practical Networking YouTube channel. You can find the videos at https://www.youtube.com/watch?v=bj-Yfakjllc&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi.
# Hosts, IP Addresses, Networks - Lesson 1a
- **Hosts**
- Hosts are any device that sends or receives traffic such as computers, laptops, phones, etc.
- Many cloud resources, such as cloud servers, can also be considered hosts.
- Also, Internet of Things, anything in your house that sends or receives traffic is also considered a host: smart TVs, speakers, smartwatches, etc.
- All those devices are sending and receiving traffic and therefore can be considered as hosts.
- All these devices follow the same rules for how they communicate to the internet.
- Hosts typically fall into one of two categories: clients or servers.
- Clients are the hosts that are initiating the request, and servers are the hosts that are responding to requests.
- Client initiates requests, and servers respond.
- Terms client and server are relative to specific communication.
- Each server you encounter is simply a computer responding to requests.
# 
- **IP Addresses**
- IP addresses are the identity of each host.
- Every host must have an IP address to communicate on the internet.
- IP addresses are stamped on every packet sent over the internet.
- Source IP address: The sender's IP.
- Destination IP address: The recipient's IP.
- IP addresses consist of 32 bits, split into four groups (octets).
- Each octet is converted to a decimal number.
- The range of each octet is from 0 to 255.
- IP addresses are typically assigned in a hierarchical manner.
- Example: Acme Corporation with offices in New York, London, and Tokyo, each assigned a range of IP addresses.
- Each office and team (sales, engineering, etc.) can have its own subset of IP addresses.
- Example of hierarchical IP address structure:
- Acme Corp: 10.x.x.x
- New York Office: 10.20.x.x
- Sales Team: 10.20.55.x
- This process of dividing IPs is known as subnetting.
#
- **Networks**
- A network is a collection of connected hosts that can communicate.
- Simplest form: Connecting two hosts forms a network.
- Before networks, data transfer required manual processes (e.g., moving data using disks).
- Networks allow hosts to share data automatically.
- Networks are logical groupings of hosts that require similar connectivity.
- Example: Home Wi-Fi network, where devices like computers and phones share similar connectivity profiles.
- Different locations (e.g., a coffee shop) may have separate networks, even though the devices have similar needs (like accessing the internet).
- Networks can contain other networks:
- Example: A school network with sub-networks for each classroom.
- These sub-networks are referred to as subnets.
- Networks connect to each other through a central resource like the internet.
- The Internet is a collection of interconnected networks.
# Hub, Bridge, Switch, Router - Network Devices - Lesson 1b
- **Intro**
- This is the second part of the lesson on network devices.
- First lesson from the first module of the networking fundamentals course.
- The goal is to teach how data flows through the internet.
- Part one covered hosts, IP addresses, and networks.
- This part will focus on two key devices: switches and routers.
#
- **Importance of Understanding Prior Concepts**
- Switches and routers can't be understood without first knowing where they come from.
- Recap from the previous video: a network is created when two computers are connected via a wire.
- When sending data across a wire, the signal decays over greater distances.
- If the computers are close, decay doesn’t matter much.
- If the computers are far apart (e.g., different buildings), decay could prevent communication.
#
- **Repeater**
- A repeater regenerates signals that decay over distance.
- Any signal that comes in on one end is regenerated out the other side.
- Repeaters allow devices that are farther apart to communicate.
#
- **Hub**
- Connecting multiple hosts directly doesn't scale well.
- Adding more hosts would mean connecting each new host to every other host.
- Solution: place a device at the center of the network to funnel communication between hosts.
- A hub is a multi-port repeater.
- Hubs regenerate signals across multiple ports.
- Example: Two hosts communicating through a hub will have their packets duplicated and sent to all ports.
- The hub solves the scaling problem but has a downside: all hosts receive all the data, even if they are not involved in the communication.
#
- **Bridges**
- Bridges solve the problem of everyone receiving everyone else's data.
- A bridge sits between sets of hosts connected by a hub.
- Bridges have two ports: one for each set of hub-connected hosts.
- Bridges learn which hosts are on which side of the bridge.
- This allows the bridge to contain communication within one side when possible.
- Example: If two hosts on one side need to communicate, the bridge ensures that the communication stays within that side and doesn’t cross to the other side.
- If hosts on opposite sides need to communicate, the bridge will allow traffic to cross.
#
- **Switches**
- Switches are a combination of hubs and bridges:
- Like hubs: multiple devices can connect to a switch.
- Like bridges: switches learn which hosts are connected to each port.
- Switches do this learning on a per-port basis.
- Example: If two hosts want to communicate, the switch knows which ports need to receive traffic and keeps the communication contained to those ports.
- If two other hosts want to communicate, the switch also keeps that traffic between their respective ports.
- Definition of a switch: a device that facilitates communication within a network.
#
- **Networks and IP Address Space:**
- A network is a logical grouping of hosts with similar connectivity needs.
- Networks share the same IP address space.
- Example: A network might own all IP addresses starting with 192.168.1.x.
- Individual hosts in the network would have unique IP addresses within this range (e.g., 192.168.1.50, 192.168.1.66).
- Example of a home Wi-Fi network:
- Devices like a printer, laptop, and phone are all part of the same network.
- Example of a classroom:
- All the PCs in a classroom could be part of the same network.
- Example of a corporate setup:
- All devices in the sales team of a London office could be part of the same network.
#
- **Multiple Networks**
- Larger setups may involve multiple networks.
- Example: A school has different classrooms, and each classroom might have its own network.
- These networks are separated because they have different connectivity requirements.
- For example: Biology classroom needs simple internet access, while the computer science classroom needs internet and cloud access.
- Switches can still facilitate communication within each network.
- Switch 1 handles communication between hosts in Network 1.
- Switch 2 handles communication between hosts in Network 2.
#
- **Routers**
- Routers handle communication between networks.
- If a host on one network wants to communicate with a host on another network, a router is required.
- Routers are also necessary to connect networks to the internet.
- Role of routers:
- Provide traffic control between networks.
- Routers allow the application of security policies, filtering, or redirection of traffic.
- Security filtering usually happens at the router level, not within a network (handled by switches).
#
- **Routers and Routing Tables**
- Routers learn which networks they are connected to.
- Example: A router learns it’s connected to Network 1 (172.16.20.x) on one side and Network 2 (172.16.30.x) on the other side.
- Routing table:
- The router’s knowledge of all the networks it knows about.
- Used to direct traffic through the correct interface.
- Gateway:
- Routers act as the default gateway for devices on the network.
- Example: A host on Network 1 uses the router’s IP address (e.g., 172.16.20.1) as its gateway to communicate with other networks.
- A gateway is a host's way out of their local network. 
#
- **Routers and Hierarchies:**
- Routers create hierarchies in networks and IP addresses.
- Example: A company like Acme Corporation has different teams and offices.
- Each office has its own networks, connected via routers.
- Routers within offices connect to other routers, eventually connecting to the internet.
- If a host in the sales team of one office wants to communicate with a host in the marketing team of another office, data is sent from router to router, traversing the internet if necessary.
#
- **The Internet as Routers:**
- The internet itself is just a collection of interconnected routers.
- Example: Data from a host in the London office could travel through multiple routers across the internet to reach the engineering team in Tokyo.
- Routers play a key role in ensuring data flows between networks across the internet.
#
- **Pulling Back Definitions (Routers and Switches):**
- Routing: the process of moving data between networks.
- A router is any device that performs routing.
- Switching: the process of moving data within networks.
- A switch is any device that performs switching.
- Other network devices perform routing or switching or both:
- Examples: access points, firewalls, load balancers, layer 3 switches, proxies, virtual routers, and virtual switches (in the cloud).
- When discussing routers and switches, the functions of routing and switching are what matters, regardless of the device performing them.
# OSI Model: A Practical Perspective - Lesson 2a
- **The OSI Model Overview**
- Networking goal: Allow two hosts to share data automatically (no manual intervention).
- Before networking, data transfer required physical interaction (e.g., plugging/unplugging a device).
- Networking automates data sharing between hosts.
- Data sharing between hosts follows a set of rules similar to languages having grammatical rules (English, Spanish, etc.).
- The rules of networking are divided into seven layers called the OSI model.
- Analogy to the Human Body:
- Just like the body has multiple systems (e.g., skeletal, nervous, cardiovascular), networking uses multiple layers.
- If each layer of the OSI model operates as intended, the goal of networking is achieved.
- The goal of networking is for hosts to share data seamlessly.
- The lesson’s goal is not just to memorize the OSI model.
- The focus is on understanding the purpose of each layer and how they contribute to the overall goal of data sharing between two hosts.
#
- **Layer 1: Physical Layer**
- Data format: Data on computers exists as bits (1s and 0s).
- The Physical Layer ensures the transport of these bits between computers.
- The physical layer encompasses any technology that moves bits from one host to another.
- Layer 1 Technologies:
- Cables (e.g., Ethernet, fiber optics) fall under Layer 1 technologies.
- The physical layer also includes Wi-Fi, which carries ones and zeros wirelessly.
- Repeaters (devices that amplify signals) are Layer 1 devices.
- Function of a repeater: Extend a wire by regenerating signals.
- Hubs (multi-port repeaters) are also Layer 1 devices.
#
- **Layer 2: Data Link Layer**
- Interaction with Layer 1: Layer 2 works with the physical layer, putting bits on the wire and retrieving them.
- Example of a Layer 2 device: Network Interface Card (NIC).
- NICs in PCs are responsible for sending/receiving bits.
- Wi-Fi access cards also operate at Layer 2.
- Function of Layer 2:
- The primary goal is hop-to-hop delivery, ensuring bits travel from one NIC to another (called a hop).
- Layer 2 Addressing Scheme:
- MAC Addresses (Media Access Control addresses) are used for Layer 2 communication.
- MAC addresses are 48 bits long, represented as 12 hex digits.
- Different systems format MAC addresses differently (e.g., Windows uses dashes, Linux uses colons, Cisco uses dots).
- Example MAC Address: A1A1 (simplified for display purposes).
- Every NIC has a unique MAC address.
- Role of Switches in Layer 2:
- Switches are Layer 2 devices that facilitate communication within a network.
- Switches help data traverse between NICs within the network.
- They allow multiple devices to connect and communicate, directing traffic internally.
- Multiple Hops in Layer 2:
- Multiple hops (moving through multiple routers) are often needed to reach distant hosts.
- Each router has a NIC with its own unique MAC address.
- Layer 2 handles delivery from one MAC address to the next, facilitating hop-to-hop delivery.
#
- **Layer 3: Network Layer**
- Goal: Ensure end-to-end delivery of data.
- Layer 3 uses IP addresses (Internet Protocol addresses) for communication.
- IP addresses are 32 bits long, represented as four octets (e.g., 192.168.1.1).
- Each host is uniquely identified by its IP address.
- Role of Routers in Layer 3:
- Routers operate at Layer 3, helping to route data across different networks.
- Hosts and anything with an IP address also operate at Layer 3.
- MAC Addresses vs. IP Addresses:
- A common question: If Layer 3 has IP addresses, why are MAC addresses needed at Layer 2?
- Answer: Each address type serves a different purpose:
- MAC addresses handle hop-to-hop delivery within the same network.
- IP addresses handle end-to-end delivery across networks.
- How Data Travels Across the Network (End-to-End):
- When a host sends data, it adds Layer 3 (IP) information, including the source IP and destination IP.
- This ensures data can reach the correct endpoint.
- The host then adds Layer 2 (MAC) information to send data to the first router.
- Routers strip and replace Layer 2 information at each hop but retain the Layer 3 (IP) information.
- Each router adds new MAC information for the next hop.
- The process repeats until the data reaches the final destination.
#
- **Layer 2 and Layer 3 Working Together**
- Layer 2 handles hop-to-hop movement (from NIC to NIC).
- Layer 3 ensures the data moves end-to-end across networks (from source IP to destination IP).
#
- **Address Resolution Protocol (ARP)**
- ARP ties Layer 3 (IP addresses) to Layer 2 (MAC addresses).
- ARP is critical for understanding how data flows through a network.
- A deeper dive into ARP is available in an article series at pracnet.net/arp.
#
- **Conclusion**
- Layer 1: Physical Layer (cables, repeaters, Wi-Fi, hubs).
- Layer 2: Data Link Layer (MAC addresses, NICs, switches, hop-to-hop delivery).
- Layer 3: Network Layer (IP addresses, routers, end-to-end delivery).
# OSI Model: A Practical Perspective - Lesson 2a
























