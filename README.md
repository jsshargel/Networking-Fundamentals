# Networking-Fundamentals
This information is here for me to learn networking fundamentals and as a source to come back to when needed. This information is from the Networking Fundamentals playlist under the Practical Networking YouTube channel. You can find the videos at https://www.youtube.com/watch?v=bj-Yfakjllc&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi.
# Hosts, IP Addresses, Networks - Networking Fundamentals - Lesson 1a
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
