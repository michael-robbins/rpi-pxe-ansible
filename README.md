# rpi-pxe-ansible
PXE Server on Raspberry Pi's with Ansible!

This current setup has been tested with:
* Raspberry Pi 2 Model B Rev 1.1
* 2021-05-07-raspios-buster-armhf-lite.zip
* 32GB SD Card
* 16GB USB Storage

# Preparing to install
1. Write the image to the SD Card
2. Mount the SD and create an empty ssh file in the boot disk
3. Ensure you assign an IP to the rpi, I use static DHCP leases
4. Ensure you change the default password, as this will be a long running rpi
5. Copy the inventory.yml.template file to inventory.yml and update the IP

# Install via Ansible
## Configure your OS's of choice
```

```

## Setup your local env
```
python3 -m venv venv
source venv/bin/activate

# Python dependencies
pip3 install --upgrade pip wheel
pip3 install --upgrade -r requirements.txt

# Ansible collections
ansible-galaxy collection install -r requirements.yml
```

## Install everything!
```
# If you haven't got keypair auth
ansible-playbook -i inventory.yml --ask-pass site.yml

# If you have!
ansible-playbook -i inventory.yml site.yml
```
