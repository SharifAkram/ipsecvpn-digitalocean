# Point to Site IPsec VPN server on Digital Ocean Droplet

This repository provides scripts and instructions
to set up an IPsec VPN on a DigitalOcean Droplet.
From the book "Set Up Your Own IPsec VPN, OpenVPN, and Wireguard Server (Build Your Own VPN)" by Lin Song.

## Features:

- Fully automated IPsec VPN server setup, no user input needed.
- Supports IKEv2 with strong and fast ciphers (e.g. AES-GCM).
- Generates VPN profiles to auto-configure iOS, macOS and Android devices.
- Supports Windows, macOS, iOS, Android, Chrome OS and Linux as VPN clients.
- Includes helper scripts to manage VPN users and certificates.
- Libreswan will be used as the IPsec server, and xl2tpd as the L2TP provider.

## Requirements:

- A DigitalOcean account
- A new Droplet (Ubuntu recommended)
- SSH and SCP access to the Droplet
- A Windows client to connect to the VPN
- doctl installed for DigitalOcean API automation

## Setup Instructions:

1. Create a DigitalOcean VPS "Droplet"
   - Sign up or log in to DigitalOcean.
   - Create a new Droplet.
   - Select datacenter region based on your requirements.
   - Select the latest Ubuntu LTS version (24.04).
   - Chose the basic shared CPU plan with regular SSD disk and 1 GB memory.
   - Create a password.
   - Enter a hostname then select create Droplet.
2. Open a terminal
   - ssh username@server-ip
3. Install IPxec VPN Server, have the script generate random VPN credentials for you.
   - > wget https://get.vpnsetup.net -O vpn.sh && sudo sh vpn.sh
4. Update Libreswan on VPN server
   - Check installed verson: ipsec --version
   - > wget https://get.vpnsetup.net/upg -O vpnup.sh && sudo sh vpnup.sh
5. Transfer the .p12 File to your Windows laptop
   - scp username@server-ip:/path/to/vpnclient.p12 /local/destination/
6. Download ikev2_config_import.cmd and save in same folder as .p12 file
   - > https://github.com/hwdsl2/vpn-extras/releases/latest/download/ikev2_config_import.cmd
7. Right click the saved script, select Properties. Click Unblock at the bottom, then click "OK"
8. Right click the script and select "Run as administrator" and follow prompts
9. Install and Configure doctl for DigitalOcean API
   - Initialize:
     - > doctl auth init
   - Login into Digital Ocean. Navigate to API. Click generate "New Token."
     Give it a name and enable permissions. Copy the token and paste it when prompted.
   - Check resources:
     - > doctl compute droplet list
   - Power On/Off:
     - > doctl compute droplet-action power-on <DROPLET_ID>
     - > doctl compute droplet-action power-off <DROPLET_ID>
   - Verify status:
     - > doctl compute droplet get <DROPLET_ID>
   - Check account balance:
     - > doctl billing balance get
10. Verification
    - Use an IP address checker before and after connecting.
    - Your IP address should match the Droplet’s public IP after connecting.
