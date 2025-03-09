# IPSec VPN on DigitalOcean

This repository provides scripts and instructions
to set up an IPSec VPN on a DigitalOcean Droplet.
The VPN allows point-to-site connections,
enabling secure access to remote resources.

## Features:

Automates VPN server setup on a DigitalOcean Droplet
Generates a .p12 certificate file for secure client authentication
Allows connection from a Windows client
Provides scripts to automate DigitalOcean resource management using doctl

## Requirements:

- A DigitalOcean account
- A new Droplet (Ubuntu recommended)
- SSH and SCP access to the Droplet
- A Windows client to connect to the VPN
- doctl installed for DigitalOcean API automation

## Setup Instructions:

1. Create a DigitalOcean Droplet/
   - a. Sign up or log in to DigitalOcean.
   - b. Create a new Droplet with Ubuntu.
   - c. Note the Droplet’s public IP address.
2. SSH into the Droplet/
   - a. ssh root@ -------
3. Install IPSec VPN Server/
   - a.
4. Transfer the .p12 File to Your Client Device/
   - a. scp root@ --------
5. Configure VPN on Windows/
6. Install and Configure doctl for DigitalOcean API/
   - a. Init
   - b. Attach API Key
   - c. Check resources
   - d. Power On/Off
   - e. Check account balance
7. Verification/
   - a. Use an IP address checker before and after connecting.
   - b. Your IP address should match the Droplet’s public IP after connecting.
