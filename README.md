# ansible-role-pitft
Set up PiTFT display for usage on a Raspberry Pi

## Prepare Raspberry Pi
1. Install RaspiOS version no later than "buster"
2. Run ```sudo raspi-config``` and select "3 Interface Options" to
      * select "P2 SSH" to set SSH server to "enabled"
      * select "P4 SPI" to enable the SPI interface
3. Run ```ip a sh | grep "inet "``` to find the Raspi's IP address on your network; connect to it using ```ssh-copy-id pi@<IP address of your Raspi>```

## Example Playbook
```
- hosts: stream-pi-client
  roles:
    - { role: joschro.pitft }
```
