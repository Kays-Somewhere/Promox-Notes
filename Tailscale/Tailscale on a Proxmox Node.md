# Installing Tailscale on a Proxmox Node
Installing Tailscale onto a Proxmox host very straightforward. This will give you access to the Node’s Web UI and ssh. 

[In the Node](#In-the-Node)

[Check-Tailscale-Status](#Check-Tailscale-Status)

[Links](#Links)

[Troubleshooting](#Troubleshooting)


## Requirements:
- Tailscale account
- Proxmox Node

# In the Node
Select the Node you want to install Tailscale on and start a shell.

To install Tailscale, run:

```
curl -fsSL https://tailscale.com/install.sh | sh
```

To start Tailscale, run:

```
tailscale up
```

Copy the provide link into a browser and add the Node to your Tailscale account.

To access the Web UI of the Node, use the following address in your browser:

```
https://\<tailscale ip\>:8006/
```

# Check Tailscale Status
To check the Tailscale status and connections run:

```
tailscale status
```

This will bring up a list of Tailscale IPs and their connection status.

# Links 
Tailscale on a Proxmox host: https://tailscale.com/kb/1133/proxmox?q=proxmox

Install Tailscale on Linux: https://tailscale.com/kb/1031/install-linux

# Troubleshooting 
E: Failed to fetch https://enterprise.proxmox.com/xxx/xxx ...
- Enterprise repos are still enabled on the Node. Disabling them will remove this error. An easy and safe way to do this is to run a post install script from Proxmox Helper Scripts (support to the project!). The script can be found at:
    - https://community-scripts.github.io/ProxmoxVE/scripts?id=post-pve-install
