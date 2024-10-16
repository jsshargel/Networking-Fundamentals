# Networking-Fundamentals
This information is here for me to learn networking fundamentals and as a source to come back to when needed. This information is from the Networking Fundamentals playlist under the Practical Networking YouTube channel. You can find the videos at https://www.youtube.com/watch?v=bj-Yfakjllc&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi. I also used an LLM to help streamline this process. 
# Network Devices - Hosts, IP Addresses, Networks - Part 1
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
# Network Devices - Hub, Bridge, Switch, Router - Part 2
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
# OSI Model: A Practical Perspective - Part 1
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
# OSI Model: A Practical Perspective - Part 2
- **Layer 4: Transport Layer**
- Purpose of Layer 4: Ensure service-to-service delivery.
- Example Scenario:
- A computer (client) has both an IP address and MAC address.
- User might have multiple programs open (e.g., a web browser, chat program, online game) that send and receive data.
- Layer 3 handles end-to-end delivery (IP header), and Layer 2 handles hop-to-hop delivery (MAC header).
- Question: How does each program receive the correct data? Answer: Layer 4.
- Layer 4’s Role:
- Distinguishes data streams and ensures each program gets the correct data.
- Layer 4 uses an addressing scheme based on ports:
- TCP (Transmission Control Protocol): Port range 0 to 65,000 (favors reliability).
- UDP (User Datagram Protocol): Port range 0 to 65,000 (favors efficiency).
- TCP and UDP provide different strategies for managing data streams.
- When data arrives, it includes a Layer 4 header that specifies which program should receive the data.
#
- **Client and Servers**
- Example of a client and three servers.
- Each server is running a specific application:
- bank.com: Listening for secure web requests via HTTPS (TCP port 443).
- site.com: Responding to general web requests via HTTP (TCP port 80).
- chat server (IRC): Running on UDP port 6667 for chat services.
- **How Port Assignment Work**
- The client makes requests to these servers using IP addresses and specific ports.
- Each program on the server is associated with a well-known port number.
- The client also assigns a random source port for each connection to track responses.
- Example: Client makes a request to site.com, using source port 9999 and destination port 80.
- The response from the server will use 9999 as the destination port, ensuring the correct program receives the response.
- **Port Management for Multiple Programs**
- The client’s use of random source ports ensures that responses for each service (browser, chat program, etc.) are delivered to the correct program.
- This mechanism also allows the client to have multiple tabs open to the same website, with each tab using a different source port to keep the data streams separate.
#
- **Layers 5, 6, and 7 (Application Layers)**
- Historically, each layer had a distinct function, but today the boundaries between these layers are vague.
- Most applications combine the functions of layers 5, 6, and 7 into a single application layer.
- The TCP/IP model simplifies this by combining layers 5, 6, and 7 into one layer.
- **Why Focus on Layers 1-4**
- The course focuses on layers 1-4, as they are the most critical for understanding how data flows through the internet.
- If you’re curious about layers 5, 6, and 7, the instructor can cover them in another video.
- For now, the TCP model’s approach is followed, treating them as a single application layer.
#
- **Encapsulation**
- Encapsulation: The process of adding headers to data as it moves down the OSI stack.
- **How Encapsulation Works**
- The host generates data that needs to be sent.
- Layer 4 (Transport Layer) adds a TCP header (includes source and destination ports) to the data. The result is called a segment.
- The segment is passed to Layer 3 (Network Layer), which adds an IP header (includes source and destination IP addresses), creating a packet.
- The Layer 2 (Data Link Layer) adds a MAC header (includes source and destination MAC addresses), forming a frame.
- The frame is then converted into ones and zeros and sent over the wire.
- **De-Encapsulation Process**
- On the receiving end, the process is reversed:
- The ones and zeros are reassembled into a frame.
- Layer 2 checks if the frame’s MAC address matches its NIC. If so, it removes the Layer 2 header and sends the data up to Layer 3.
- Layer 3 checks the IP address and passes the data to Layer 4 if the IP matches.
- Layer 4 delivers the data to the correct application based on the port number.
#
- **The OSI Model and Device Operation**
- Devices like switches and routers operate at specific layers:
- Switches: Layer 2 (They only look at the Layer 2 header when making decisions).
- Routers: Layer 3 (They examine the Layer 3 header).
- **Protocols also operate at specific layers**
- IP: Layer 3 protocol.
- TCP/UDP: Layer 4 protocols.
- **Exceptions in Networking Devices and Protocols**
- Some devices can interact with multiple layers:
- Example: A router typically operates at Layer 3, but if an access list is configured, it may inspect the Layer 4 header to make filtering decisions.
- ARP Protocol: Links Layer 2 and Layer 3 by connecting MAC addresses to IP addresses (doesn’t fit neatly into either layer).
#
- **Conclusion**
- The OSI model is a conceptual model to understand data flow, but it’s not a rigid set of rules.
- **Main Takeaways**
- Each OSI layer has a specific function that contributes to the overall goal of allowing two hosts to share data.
- Each layer uses its own addressing scheme (MAC for Layer 2, IP for Layer 3, Ports for Layer 4).
- Devices and protocols operate at specific layers but exceptions do exist.
# Everything Hosts do to speak on the Internet - Lesson 3 - Part 1
- This lesson focuses on the internet from the host’s perspective.
- The lesson will cover how hosts communicate over the internet.
- This lesson focuses on how hosts communicate across two scenarios:
- Scenario 1: Two hosts directly connected.
- Scenario 2: Two hosts communicating across a router.
#
- **Scenario 1: Two Hosts on the Same Network**
- **Direct Connection:**
- Hosts do not know they are directly connected.
- Even if connected through a switch, hosts follow the same steps.
- **Network Interface Card (NIC):**
- Both hosts have a NIC, giving them a MAC address.
- IP addresses and subnet masks are also assigned.
- **Subnet Mask:**
- The subnet mask defines the size of the network.
- (No detailed discussion on subnetting, but links to additional resources provided.)
- **Host A Sending Data to Host B**
- **Data Sending:**
- Host A has some data to send to Host B.
- From a network perspective, the data is just ones and zeros.
- **IP Address Knowledge:**
- Host A knows the IP address of Host B (through DNS or manual entry like ping).
- Host A knows the destination IP is on the same network by comparing it to its subnet mask.
- **Layer 3 (IP Header):**
- Host A creates a Layer 3 header for end-to-end delivery.
- Includes:
- Source IP (Host A).
- Destination IP (Host B).
#
- **Layer 2 (MAC Address Resolution)**
- Problem: Host A does not know Host B’s MAC address.
- ARP Protocol:
- Address Resolution Protocol (ARP) is used to resolve the MAC address.
- ARP links a Layer 3 (IP) address to a Layer 2 (MAC) address.
- **ARP Request**
- Host A sends an ARP request:
- Asks for the MAC address associated with Host B’s IP.
- Includes Host A’s MAC and IP address.
- Layer 2 Broadcast:
- ARP request is sent as a broadcast to all devices on the network.
- Broadcast uses a destination MAC address of FF:FF:FF:FF:FF
- (reserved MAC address for broadcasts).
- **ARP Response**
- Host B's ARP Cache:
- Host B receives the ARP request and stores Host A’s IP-MAC mapping in its ARP cache.
- Unicast Response:
- Host B sends an ARP response directly to Host A.
- Includes Host B’s IP and MAC address.
- Host A’s ARP Cache:
- Host A now stores Host B’s MAC address in its ARP cache.
#
- **Data Transmission After ARP Resolution**
- **Layer 2 Header Creation:**
- Now that Host A knows Host B’s MAC address, it completes the Layer 2 header.
- Includes:
- Source MAC (Host A’s MAC address).
- Destination MAC (Host B’s MAC address).
- **Data Sent:**
- Data is sent from Host A to Host B via Layer 2 and Layer 3 headers.
- Layer 2 ensures hop-to-hop delivery.
#
- **Host B Receives the Data**
- **Layer 2 Header Discarded:**
- Host B receives the data and discards the Layer 2 header (it’s served its purpose).
- **Layer 3 Header Discarded:**
- Host B also discards the Layer 3 header once the data arrives, since the data has reached its destination.
- **Application Layer:**
- The application on Host B can now process the received data.
#
- **Conclusion of Host A to Host B Communication**
- **Reply from Host B:**
- Host B will likely need to send a response back to Host A.
- The response is faster now because:
- Host B has Host A’s IP and MAC in its ARP cache.
- It can create Layer 3 and Layer 2 headers quickly.
- **Further Communication:**
- Any further data exchanges between Host A and Host B will happen easily as both have the necessary MAC and IP information stored in their respective ARP caches.
# Everything Hosts do to speak on the Internet - Lesson 3 - Part 2 
- In part 2 of this lesson, we will add a router and explore how hosts communicate with another host on a foreign network.
#
- **Scenario 2: Host A Communicating with Host C Through a Router**
- **Topology Overview:**
- Host A wants to send data to Host C, and there's a router between them.
- Both hosts and the router have MAC addresses and IP addresses.
- The /24 notation is used to represent the subnet mask for each device.
- **Subnet Mask:**
- The subnet mask defines the size of a network.
- (Reminder: subnetting isn’t covered in this module; additional resources are available for learning subnetting.)
#
- **Host A Preparing to Send Data to Host C**
- **ARP Cache:**
- Host A, the router, and Host C all have IP addresses and thus have ARP caches.
- In this lesson, we focus on Host A’s ARP cache.
- **Knowing Host C’s IP Address:**
- Host A already knows Host C’s IP address (provided by the user or an application).
- Host A can determine that Host C is on a foreign network by comparing IP addresses and subnet masks.
- **Creating a Layer 3 Header:**
- Host A creates a Layer 3 header (IP header) to identify the communication endpoints.
- The source IP is Host A, and the destination IP is Host C.
#
- **Host A Creating a Layer 2 Header**
- **Layer 2 Header Function:**
- Layer 2 handles hop-to-hop delivery.
- Since Host C is on a foreign network, Host A needs to send the data to the router first.
- **ARP Resolution for the Router:**
- Host A’s ARP cache is empty, so it doesn’t know the router’s MAC address.
- Host A must use ARP to resolve the router's MAC address.
- **Default Gateway Configuration:**
- Host A knows the router’s IP address because it is configured as the default gateway.
- **In a typical network setup, you configure:**
- IP address
- Subnet mask
- Default gateway (the router’s IP)
- **IP Configuration Example:**
- Host A’s IP: Matches its configuration.
- Subnet mask: /24.
- Default gateway: The router’s IP address.
#
- **Using ARP to Resolve the Router’s MAC Address**
- **Sending an ARP Request:**
- Host A sends an ARP request asking for the MAC address associated with the router’s IP.
- The ARP request also includes Host A’s MAC address.
- **Router’s ARP Response:**
- The router sends an ARP response back to Host A, mapping its IP address to its MAC address (e.g., 10.1.1.1 → E5).
- **Populating Host A’s ARP Cache:**
- Host A populates its ARP cache with the router’s MAC address, allowing it to send data to the router.
#
- S**ending Data to the Router**
- **Creating the Layer 2 Header:**
- Host A completes the Layer 2 header with:
- Source MAC: Host A’s MAC address.
- Destination MAC: The router’s MAC address.
- The Layer 2 header will handle hop-to-hop delivery to the router.
- **Sending the Data:**
- Host A sends the data to the router.
- **Router’s Role:**
- Upon receiving the data, the router discards the Layer 2 header (its job is done).
- The router will then add any necessary Layer 2 headers to continue forwarding the packet through additional hops.
#
- **ARP Reuse for Foreign Networks**
- **Reusing the ARP Entry:**
- The ARP entry Host A used to send data to the router can be reused for communication with any host on a foreign network.
- **Layer 2 Header Consistency:**
- The Layer 2 header remains the same for all communication with foreign networks since the first hop is always the router.
- **Example with Additional Hosts:**
- Host A can now communicate with Host D by simply creating a new Layer 3 header with the destination IP of Host D.
- The Layer 2 header (MAC addresses) stays the same because the first hop is still the router.
#
- **ARP's Role in Network Communication**
- **ARP’s Crucial Role:**
- ARP is crucial for data transmission because it allows hosts to resolve MAC addresses based on IP addresses.
- The first step for any host when sending data is to determine if the target IP is on:
- The local network (resolve the target’s MAC directly).
- A foreign network (resolve the default gateway’s MAC).
- **ARP Process Summary:**
- If the target is on the local network, ARP resolves the target’s MAC.
- If the target is on a foreign network, ARP resolves the default gateway’s MAC.
#















