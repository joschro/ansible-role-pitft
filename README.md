ansible-role-pitft
==================

Set up PiTFT display for usage on a Raspberry Pi.

Requirements
------------

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

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: joschro.pitft }


License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
