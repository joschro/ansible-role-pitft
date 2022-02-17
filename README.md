ansible-role-pitft
==================

Set up PiTFT display for usage on a Raspberry Pi, as described in https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi/easy-install-2 .


Requirements
------------

1. A Raspberry Pi with RaspiOS (including graphical desktop environment) installed.
2. An Adafruit touchscreen display like this installed: https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi

Prepare Raspberry Pi
1. Install RaspiOS version no later than "buster"
2. Run ```sudo raspi-config``` and select "3 Interface Options" to
      * select "P2 SSH" to set SSH server to "enabled"
      * select "P4 SPI" to enable the SPI interface
3. Run ```ip a sh | grep "inet "``` to find the Raspi's IP address on your network; connect to it using ```ssh-copy-id pi@<IP address of your Raspi>```


Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

This Playbook uses the following roles from Ansible Galaxy:
  - joschro.pitft

Example Playbook
----------------

Create a playbook file (e.g. ansible-playbook-pitft.yml) with the following content on the Raspberry Pi you want to make the display work after successful RaspiOS installation:
```
---
# Ansible Playbook to set up a Raspberry Pi to make a Adafruit display work
- name: Set up a Adafruits 2.8 capacitive touchdisplay
  hosts: localhost
  gather_facts: no
  roles:
    - { role: joschro.pitft }
```
Create a requirements.yml file in the same directory:
```
# Install a role from the Ansible Galaxy
#- src: joschro.pitft

# Install a role from GitHub
- name: joschro.pitft
  src: https://github.com/joschro/ansible-role-pitft
```

You can now run the two commands on the command line to run the installation:
```
ansible-galaxy install -r requirements.yml --force
ansible-playbook -i localhost ansible-playbook-pitft.yml
```


License
-------

GPLv3

Author Information
------------------

joschro
