# Subnetting

# Understanding and Performing Subnetting

Breaking a large network into smaller subnets, known as subnetting, helps manage and organize network traffic more efficiently. Here’s a simple way to understand and perform subnetting with an example:

## What is Subnetting?
Subnetting involves dividing a large network into smaller, manageable sub-networks (subnets). This helps in organizing networks, improving security, and optimizing performance.

# Breaking a Network Into Smaller Subnets: Detailed Breakdown

## Example Scenario
You have a large network with the IP address `192.168.1.0/24` and want to divide it into smaller subnets.

## Steps to Subnet a Network

### 1. Determine How Many Subnets You Need
Assume you need 4 subnets.

### 2. Calculate the New Subnet Mask
To create 4 subnets, you need to borrow bits from the host portion of the address to create additional network bits:

- **Original Network Mask:** `/24` (255.255.255.0)
- **Required Subnets:** 4, which means you need 2 additional bits (since \(2^2 = 4\)).

The new subnet mask will be:
- **New Subnet Mask:** `/24 + 2 = /26` (255.255.255.192)

### 3. Calculate the Number of IP Addresses per Subnet
With a `/26` subnet mask:
- **Number of Host Bits:** 32 - 26 = 6
- **Total IP Addresses per Subnet:** \(2^6 = 64\)

### 4. Calculate Usable IP Addresses per Subnet
Each subnet has:
- **Total IP Addresses:** 64
- **Reserved Addresses:**
  - **Network Address:** 1 (the first address in the subnet, not usable for hosts)
  - **Broadcast Address:** 1 (the last address in the subnet, not usable for hosts)
- **Usable IP Addresses:** \(64 - 2 = 62\)

### 5. Define the New Subnets
With a `/26` subnet mask, the new subnets are:

- **Subnet 1:** `192.168.1.0/26`
  - **Network Address:** `192.168.1.0`
  - **Usable IP Range:** `192.168.1.1` to `192.168.1.62`
  - **Broadcast Address:** `192.168.1.63`

- **Subnet 2:** `192.168.1.64/26`
  - **Network Address:** `192.168.1.64`
  - **Usable IP Range:** `192.168.1.65` to `192.168.1.126`
  - **Broadcast Address:** `192.168.1.127`

- **Subnet 3:** `192.168.1.128/26`
  - **Network Address:** `192.168.1.128`
  - **Usable IP Range:** `192.168.1.129` to `192.168.1.190`
  - **Broadcast Address:** `192.168.1.191`

- **Subnet 4:** `192.168.1.192/26`
  - **Network Address:** `192.168.1.192`
  - **Usable IP Range:** `192.168.1.193` to `192.168.1.254`
  - **Broadcast Address:** `192.168.1.255`

## Summary
- **Original Network:** `192.168.1.0/24`
  - **Total IP Addresses:** 256
  - **Usable IP Addresses:** 254

- **After Subnetting into `/26`:**
  - **Number of Subnets:** 4
  - **Total IP Addresses per Subnet:** 64
  - **Usable IP Addresses per Subnet:** 62
  - **Network Address per Subnet:** 1 (not usable by hosts)
  - **Broadcast Address per Subnet:** 1 (not usable by hosts)

By dividing the original network into smaller `/26` subnets, you create 4 manageable segments, each with 62 usable IP addresses, improving organization and network efficiency.
