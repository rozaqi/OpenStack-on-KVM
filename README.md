# OpenStack-on-KVM

Spesifikasi Server
RAM : 58GB
VCPU : -
OS : Ubuntu

### 1. Install KVM
```
sudo apt update
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils
sudo adduser <user> libvirt
sudo adduser <user> kvm
```

### 2. Create KVM Virtual Machine

#### Create Virtual Network in KVM
1. nano <nama-file>.xml
```
<network>
  <name>net-172.18.234</name>
  <forward mode='route'/>
  <ip address='172.18.234.1' netmask='255.255.255.0'>
    <dhcp>
    </dhcp>
  </ip>
</network>
```
ip address disesuaikan
2. virsh net-define <nama-file>.xml
3. virsh net-start <nama-file>.xml
4. virsh net-autostart <nama-file>.xml
  
### 3. Install OpenStack using Ansible

