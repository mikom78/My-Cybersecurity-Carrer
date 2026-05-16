1. ***Port Forwarding**
    -Think of your router like a security guard at the front gate of an apartment
    building. By default, the guard blocks everyone from coming in. Port forwarding is like giving the  guard a specific instruction: _"If someone asks for Port 22 (SSH), send them straight to Laptop3."
    -You use this when you want to host a service (like a web server or a game) on your local    network so that people from the outside internet can reach it.
2. **Firewalls**
    -is a security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules.
   ###### -Firewall Categories 
     - **Packet Filtering (Stateless):** The simplest type. It looks at each packet individually (IP address, port number) and decides to "Allow" or "Block" based on a list. It doesn’t remember the "conversation."
     - **Stateful Inspection:** Smarter. It remembers the state of active connections. If you sent a request out, it knows the "reply" coming back is safe.
     - **Next-Generation Firewall (NGFW):** These are the modern "super-guards." They don't just look at addresses; they look at the actual data inside the packet to see if it contains malware or suspicious behavior.
3. **VPN(Virtual Private Network)**
   -creates a secure "tunnel" between your device and a server. it will do->
    - **Encryption:** your data is scrambled so your ISP or a hacker  sniffs your traffic, they can't see your data.
    - **Masking:** Your real IP address will be hidden, & you will appear in browser from the VPN server location.  
   ###### -Common protocols->  
    - OpenVPN: very secure & widely used.
    - WireGuard: The new standard faster & more modern.
    - IPsec: often used for business to business connections.
4. **LAN(Local Area Networks)**
    -physical tools that will be contained in LAN->
     1. **Switch**
        -The "Brain" of the local network. it connects devices (PCs, Printers) and sends data only to the specific device that needs it using **MAC Addresses**.
     2. **Router**
        -The "Gateway" It connects your local network (LAN) to the outside internet (WAN) using **IP Addresses**.
     3. **VLAN(Virtual Local Area Network**
        -allows specific devices within a network to be virtually split up. This split means they can all benefit from things such as an Internet connection but are treated separately. This network separation provides security because it means that rules in place determine how specific devices communicate with each other. This segregation is illustrated in the diagram below: