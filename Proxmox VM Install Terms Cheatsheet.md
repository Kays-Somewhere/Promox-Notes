# Proxmox VM Creation Terms Cheatsheet (ver 8.3)
Definition of terms and options seen during the VM creation process

## General
Node: Physical location where VM will be hosted

VM ID: Numeric number assigned to VM
- Can be auto or manually assigned a number
- Only used for identification

Name: Assigned name
- Only used for identification

Resource Pool: logical group of VMs for organization or group permission purposes

## OS
### Use CD/DVD
Storage: Location where ISO image stored

ISO Image: ISO file of operating system, must end in .iso

Type: Operating System type (Windows, Linux, etc)

Version: Year of operating sytem, kernel version

## System
Graphics Card: Virtual display adapter 
- Default is typically fine

Machine: Layout of the VMs Virtual Motherboard
- Default is typically fine

SCSI Controller: Controls communication between the VM and devices (storage)
- Default is typically fine

QEMU Agent: Indicates whether Guest Agent is installed 

BIOS: BIOS or firmware interface VM is built on

Add TPM: Add a trusted platform module

## Disks
Bus/Devices: Virtual disk interface

Storage: Storage location of VM on chosen Node (Selected Node in General Section)

Disk Size: Amount of storage allocated to VM

Cache: Affects how disk write operations are done

Discard: Shrinks storage space if space is unused/deleted
- only available with Thin Provisioning

IO Thread: Creates threads for each storage device outside of the main thread
- Only available with some SCSI controllers

Format: Format type of the storage

## CPU
Sockets: number of CPU VM can use

Cores: Number of Cores that VM can use

Type: CPU type that VM will use

## Memory
Memory: Amount of RAM allocated 

Ballooning (under Advanced): Allows VM to take more RAM than allocated and give back unused RAM

## Network
No Network: Do not setup a network on VM

Bridge: Network bridge used

VLAN Tag: VLAN VM is located on

Model: Type of virtual Network Interface Controller (NIC) will use

MAC Address: MAC address of the VM
- Can be auto or manually assigned

Firewall: Indicates whether Proxmox's Firewall should be used
