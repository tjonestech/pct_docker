# pct_docker
Popcorn Time Docker Configuration

Goals: Contain Popcorn Time (PCT) for Security Isolation

       Ensure PTC traffic is encapsulated in a VPN tunnel
       
       Ideally a persistent PTC DB
       
       Hardened container

Implimentation Ideas:

       NordVPN
       
       Xorg Window (What's faster/better looking?)
       
       
       
@TODO Ubuntu Base  https://docs.docker.com/install/linux/docker-ce/ubuntu/

@TODO Install Popcorn-Time https://github.com/jerivasuaq/popcorntime

@TODO Xorg Window http://wiki.ros.org/docker/Tutorials/GUI https://github.com/mviereck/x11docker

@TODO Configure Nord VPN https://github.com/bubuntux/nordvpn https://github.com/jotyGill/openpyn-nordvpn

@TODO Configure VPN KillSwitch https://github.com/jotyGill/openpyn-nordvpn

@TODO Persistent Storage for local db https://docs.docker.com/storage/volumes/#populate-a-volume-using-a-container

@TODO Harden ports

@TODO Harden docker https://www.digitalocean.com/community/tutorials/how-to-audit-docker-host-security-with-docker-bench-for-security-on-ubuntu-16-04

@TODO Harden SELinux/AppArmor profiles

@TODO Harden no_new_priv

@TODO Harden Vault

@TODO Meta Data https://docs.docker.com/config/labels-custom-metadata/#manage-labels-on-objects

@TODO Pefromance Packer

@TODO Desktop Icon for Launch

       sudo wget -qO /opt/popcorn-time/popcorntime.png goo.gl/wz8ifr
       
