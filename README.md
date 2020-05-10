# ansible-seedbox-jellyfin-server

## Description :

I share you the playbook that I use to deploy my seedbox installation using :
- Flood and rtorrent : https://hub.docker.com/r/romancin/rutorrent-flood
- Jellyfin : https://hub.docker.com/r/linuxserver/jellyfin

### Requirements :

A Debian running machine (or an other Debian OS based).
A root user or an user with sudo privileges.

### Files and folders description

deploy-seedbox.yml : list of role to deploy and the common variables. For instance, here you can edit you timezone or remove role from deployment.

roles/ : contains the roles used by the playbook deploy-seedbox.yml

hosts/ : contains the hosts file used by the playbook. Here you can define the IP addresses you wan to deploy.

## Usage

### Clone the repository :

    git clone https://github.com/jserlan/ansible-seedbox-jellyfin-server.git

### Run the playbook :

    ansible-playbook --user $USERNAME --ask-pass --become --ask-become-pass -i hosts/seedbox deploy-seedbox.yml

Playbook arguments :

    --ask-pass/-k : used if you didn't store your ssh key on the remote machine (optional)

    --become : used if your user need sudo to be granted privileges (optional)

    --ask-become-pass : used if your user need to set the password for each sudo command (optional)

    --inventory : set the host file that contains the seedbox group with the IP address(es) to deploy (mandatory)

    --user : set the remote user (mandatory)

## Configuration

### Jellyfin :

Once the playbook installation is finished, you can reach Jellyfin by connecting to http://<your IP>:8096/ to set the configuration.

### Flood/rtorrent :

One the playbook installation is finished for Flood and rTorrent, you can reach Flood by connecting to http://<your IP>:3000/ to set the configuration.
