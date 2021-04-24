# Spectrum Playbooks
ansible playbooks for installing CA / Broadcom DX Netops Spectrum


## remove sradmin
sudo systemctl disable sradmin --now

sudo rm -rf /sw/ /etc/init.d/sradmin
