# Troubleshooting Proxmox Nodes, Containers, and VMs
[Nodes](#Nodes)

[Containers](#Containers)

---

# Nodes
## Shell
### E: Failed to fetch https://enterprise.proxmox.com/xxx/xxx ...
- Enterprise repos are still enabled on the Node. Disabling them will remove this error. An easy and safe way to do this is to run a post install script from Proxmox Helper Scripts (support to the project!). The script can be found at:
    - https://community-scripts.github.io/ProxmoxVE/scripts?id=post-pve-install

## Web UI
### The connection has timed out
1- Check that node is correctly connected to the router
  - Is the ethernet cable plugged into the node AND the router?
  - Is the ethernet cable damaged?
  - Is the router on?
  - Are you on the correct wifi network?
  - Are you connecting to the the right https address (ip and port)?

2- If everything looks good in Step 2: Reinstall Proxmox on the node

---

# Containers
### Bash: curl: command not found
- Update the container using: sudo apt-get update
