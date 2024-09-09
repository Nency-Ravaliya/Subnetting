# Subnetting

# Understanding and Performing Subnetting

Breaking a large network into smaller subnets, known as subnetting, helps manage and organize network traffic more efficiently. Here’s a simple way to understand and perform subnetting with an example:

## What is Subnetting?
Subnetting involves dividing a large network into smaller, manageable sub-networks (subnets). This helps in organizing networks, improving security, and optimizing performance.

## Example Scenario
Let’s say you have a large network with the IP address `192.168.1.0/24`. This means you have a single network with a subnet mask of `255.255.255.0`, which provides you with 256 IP addresses (from `192.168.1.0` to `192.168.1.255`).

You want to divide this network into smaller subnets to better organize your network. Here’s how you can do it:

## Steps to Subnet a Network

### 1. Determine How Many Subnets You Need
Assume you need 4 subnets.

### 2. Calculate the New Subnet Mask
To create 4 subnets, you need to borrow bits from the host part of the address to create additional network bits.

- Start with `/24` (original network mask)
- You need enough bits to create 4 subnets. For 4 subnets, you need 2 bits (since \(2^2 = 4\)).

So, add these 2 bits to the original `/24` network mask:
- New subnet mask = `/24 + 2 = /26`

### 3. Calculate the Number of IP Addresses per Subnet
- A `/26` subnet mask has 26 network bits and 6 host bits (32 - 26 = 6).
- Number of IP addresses per subnet = \(2^6 = 64\)

### 4. Define the New Subnets
With a `/26` subnet mask, each subnet has 64 IP addresses. The network address for each subnet will be:

- **Subnet 1:** `192.168.1.0/26`  
  Range: `192.168.1.0` to `192.168.1.63`  
  (Network address: `192.168.1.0`, Broadcast address: `192.168.1.63`)

- **Subnet 2:** `192.168.1.64/26`  
  Range: `192.168.1.64` to `192.168.1.127`  
  (Network address: `192.168.1.64`, Broadcast address: `192.168.1.127`)

- **Subnet 3:** `192.168.1.128/26`  
  Range: `192.168.1.128` to `192.168.1.191`  
  (Network address: `192.168.1.128`, Broadcast address: `192.168.1.191`)

- **Subnet 4:** `192.168.1.192/26`  
  Range: `192.168.1.192` to `192.168.1.255`  
  (Network address: `192.168.1.192`, Broadcast address: `192.168.1.255`)

## Summary
By subnetting the original `192.168.1.0/24` network into `/26` subnets:
- You created 4 smaller subnets.
- Each subnet has 64 IP addresses.
- Each subnet is independent, allowing better organization and management.

## Benefits of Subnetting
- **Efficient IP Address Use:** Reduces wasted IP addresses.
- **Improved Security:** Can segment sensitive parts of the network.
- **Better Performance:** Limits broadcast traffic within each subnet.

Subnetting helps in managing large networks more effectively by creating smaller, manageable segments.
