# ansible-playbook-seedbox

## Description :

The role will deploy a seedbox installation using rtorrrent with Flood GUI and Jellyfin for the mediacenter

The Docker images used :
- Flood and rtorrent : https://hub.docker.com/r/romancin/rutorrent-flood
- Jellyfin : https://hub.docker.com/r/linuxserver/jellyfin

### Requirements :

A Linux machine and a root user or at least an user with sudo privileges.

Validate on : Debian 11 and over, Ubuntu 20 and over.

### Files and folders description

deploy-seedbox.yml : list of role to deploy and the common variables. For instance, here you can edit you timezone or remove role from deployment.

ansible.cfg : contains my custom parameters for ansible.

roles/ : contains the roles used by the playbook deploy-seedbox.yml

hosts/ : contains the hosts file used by the playbook. Here you can define the IP addresses you wan to deploy.

## Usage

### Clone the repository :

    git clone https://github.com/jserlan/ansible-playbooks-seedbox.git

### Run the playbook :

    ansible-playbook -k -b -K -u $USERNAME -i hosts/default deploy-seedbox.yml

Playbook arguments :

    -k (or --ask-pass) : used if you didn't store your ssh key on the remote machine (optional)

    -b (or --become) : used if your user need sudo to be granted privileges (optional)

    -K (or --ask-become-pass) : used if your user need to set the password for each sudo command (optional)

    -i (or --inventory) : set the host file that contains the seedbox group with the IP address(es) to deploy (mandatory)

    -u (or --user) : set the remote user (mandatory)

## Configuration

### Jellyfin :

Once the playbook installation is finished, you can reach Jellyfin by connecting to `http://<your IP>:8096/` to set the configuration.

### Flood/rtorrent :

One the playbook installation is finished for Flood and rTorrent, you can reach Flood by connecting to `http://<your IP>:3000/` to set the configuration.
