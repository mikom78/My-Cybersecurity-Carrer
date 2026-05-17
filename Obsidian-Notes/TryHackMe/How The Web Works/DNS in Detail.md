1. **DNS(Domain Name System)**
    -provides a simple way for us to communicate with devices on the internet without remembering complex numbers. every computer on the internet has its own unique address to communicate with it called an **IP address**.
    -When you want to visit a website, it's not exactly convenient to remember this complicated set of numbers, and that's where DNS can help. So instead of remembering 104.26.10.229, you can remember **tryhackme.com** instead.
2. **Domain Hierarchy**
    1. <mark>**Root Domain**</mark>
        -is the main, registered part of a website address, consisting of the second-level domain and the top-level domain (TLD), like **tryhackme.com**.
    2. <mark>**TLD(Top Level Domain)**</mark>
        -it's the right hand of a Domain name. There are two types of a TLD->
         1. gTLD(General TLD)
             -Historically a gTLD was meant to tell the user the domain name's purpose; for example, a .com would be for commercial purposes, .org for an organization, .edu for education and .gov for government. but Due to such demand, there is an influx of new gTLDs ranging from .online , .club , .website , .biz and so many more.
         2. ccTLD(Country Code TLD)
             -was used for geographical purposes, for example, .ca for sites based in Canada, .co .uk for sites based in the United Kingdom and so on.
    3. <mark>**SLD(Second Level Domain)**</mark>
        -Taking tryhackme.com as an example, the tryhackme is the Second Level Domain. When registering a domain name, the second-level domain is limited to 63 characters + the TLD and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens).
    4. <mark>**SubDomain**</mark>
        -it sits on the left-hand side of the Second-Level Domain using a period to separate it. e.g:- **admin.tryahckme.com** the "admin" part is the subdomain. it have the same restrictions as SLD, being limited to 63 characters and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens). You can use multiple subdomains split with periods to create longer names, such as ale.admin.tryhackme.com But the total domain length must be kept to 253 characters or less. There is no limit to the number of subdomains you can create for your domain name.
    5. e.g:- by Image ![](/images/Domain_Hierarchy.png)
3. **DNS Record**
    -is often described as the **"phonebook of the internet"**. that are instructions stored on authorization DNS servers that translate human-readable domain names into computer-readable IP address. common types of DNS records ->
    1. <mark>**NS(Name Server) Records**</mark>
        -Delegates a DNS zone to use specific authoritative name servers that are responsible for the **SLD(Second Level Domain)** .
	2. <mark>**A Records**</mark>
        -Maps a domain/subdomain to an IPv4 address.
    3. <mark>**AAAA Records**</mark>
        -Maps a domain/subdomain to an IPv6 address.
    4. <mark>**CNAME(Canonical Name) Records**</mark>
        -it Aliases one domain name to another. e.g:-  TryHackMe's online shop has the subdomain name **store.tryhackme.com** which returns a CNAME record **shops.shopify.com**. Another DNS request would then be made to **shops.shopify.com** to work out the IP address.
    5. <mark>**MX(Mail Exchange) Records**</mark>
        -Directs email to a specific mail server.
    6. <mark>**TXT(Text) Record**</mark>
        -are free text fields where any text-based data can be stored. TXT records have multiple uses, but some common ones can be to list servers that have the authority to send an email on behalf of the domain (this can help in the battle against spam and spoofed email) & for domain ownership verification.
4. **DNS Request**
    1. When you request a domain name, your computer first checks its **local cache** to see if you've previously looked up the address recently; if not, a request to your Recursive DNS Server will be made.
    2. 1. **A Recursive Resolver DNS** Server is usually provided by your **ISP**, but you can also choose your own. This server also has a local cache of recently looked up domain names. If a result is found locally, this is sent back to your computer, and your request ends here (this is common for popular and heavily requested services such as Google, Facebook, Twitter). If the request cannot be found locally, a journey begins to find the correct answer, starting with the internet's root DNS servers.
    3. 1. **The root** servers act as the DNS backbone of the internet; their job is to redirect you to the correct Top Level Domain Server, depending on your request. If, e.g:- you request www.tryhackme.com, the root server will recognize the Top Level Domain of .com and refer you to the correct TLD server that deals with .com addresses.
    4. 1. **The TLD** server holds records for where to find the authoritative server to answer the DNS request. **The authoritative** server is often also known as the **nameserver** for the domain. e.g:- the name server for **tryhackme.com** is **kip.ns.cloudflare.com** and **uma.ns.cloudflare.com**. You'll often find multiple nameservers for a domain name to act as a backup in case one goes down.
    5. **An authoritative DNS** server is the server that is responsible for storing the DNS records for a particular domain name and where any updates to your domain name DNS records would be made. Depending on the record type, the DNS record is then sent back to the **Recursive DNS** Server, where a local copy will be cached for future requests and then relayed back to the original client that made the request. DNS records all come with a **TTL (Time To Live)** value. This value is a number represented in seconds that the response should be saved for locally until you have to look it up again. Caching saves on having to make a DNS request every time you communicate with a server.
        - <mark>**TTL(Time To Live)**</mark>->refers to the amount of time or “hops” that a packet is set to exist inside a network before being discarded by a router. TTL it's also used in **CDN caching** and **DNS caching**.
    6. e.g:- by Image ![](/images/DNS_request_proccess.png)




