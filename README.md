# Point to Site IPsec VPN server on Digital Ocean Droplet

This repository provides scripts and instructions
to set up an IPsec VPN on a DigitalOcean Droplet.
The VPN allows point to site connections,
enabling secure access to remote resources.

## Features:

* VPN server setup on a DigitalOcean Droplet.
* Generates a .p12 certificate file for secure client authentication.
* Allows connection from a Windows client.
* Provides scripts to automate DigitalOcean resource management using doctl.

## Requirements:

- A DigitalOcean account
- A new Droplet (Ubuntu recommended)
- SSH and SCP access to the Droplet
- A Windows client to connect to the VPN
- doctl installed for DigitalOcean API automation

## Setup Instructions:

1. Create a DigitalOcean Droplet
   - Sign up or log in to DigitalOcean.
   - Create a new Droplet with Ubuntu.
   - Note the Droplet’s public IP address.
2. SSH into the Droplet
   - ssh root@ -------
3. Install IPSec VPN Server
4. Transfer the .p12 File to Your Client Device
   - scp root@ --------
5. Configure VPN on Windows
6. Install and Configure doctl for DigitalOcean API
   - Init
   - Attach API Key
   - Check resources
   - Power On/Off
   - Check account balance
7. Verification
   - Use an IP address checker before and after connecting.
   - Your IP address should match the Droplet’s public IP after connecting.
