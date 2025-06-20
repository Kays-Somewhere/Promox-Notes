# Suricata Troubleshooting and Install
https://suricata.io/

# Install
Use the following guide to download Suricata in a lxc container.

Guide: https://docs.suricata.io/en/latest/quickstart.html

Container Template: Ubuntu 22.04

# Troubleshooting

### Step 2.5 Alerting

Trigger:

```
sudo tail -f /var/log/suricata/fast.log
curl http://testmynids.org/uid/index.html
```

#### No Responce/Output
- Wait a minute then ctrl+C to cancel
- If error 'Curl: command not found'
  - Run
    ```
    apt install curl
    ```

#### Actual Results not matching Expected
Expected result: alert ip any any -> any any (msg:"GPL ATTACK_RESPONSE id check returned root"; content:"uid=0|28|root|29|"; classtype:bad-unknown; sid:2100498; rev:7; metadata:created_at 2010_09_23, updated_at 2010_09_23;)

Actual result: 06/20/2025-15:30:29.415984  [**] [1:2200122:1] SURICATA AF-PACKET truncated packet [**] [Classification: Generic Protocol Command Decode] [Priority: 3] [**] [Raw pkt: AA 00 00 CC F0 ... ]

<ins>**What is happening? **</ins>
  - A truncated packet means that only a portion of a packet is captured, not the whole thing.

<ins>**Fix**</ins>
  - Edit the config file
  ```
  nano /etc/suricata/suricata.yaml
  ```
  - Find the 'af-packet:' section
    - ![image](https://github.com/user-attachments/assets/563b7481-a2d3-4532-8780-72cd64b7f4ab)
  - Find '- interface:' at the bottom of the section
    - ![Screenshot 2025-06-20 120728](https://github.com/user-attachments/assets/70f154a1-8577-4bae-b8ad-614eec42f12f)
  - Delete the '#' in front of 'threads: auto'
  - Save and exit the file
  - reboot
  - Rerun the trigger
