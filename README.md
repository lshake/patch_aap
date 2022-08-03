# Patch AAP2 Nodes

Simple playbook to safely patch the base OS for AAP 2.1 and 2.2 Nodes.  
All repositories are disabled except for the base OS repositories for RHEL8 and RHEL9.  
AAP Packages are excluded based on those listed here : https://access.redhat.com/solutions/4566711

The AAP version can be set via the aap_version variable and can be overrided as required. 

A crude reboot option allows the machines to be restarted based on the state of needs-restarting.
Provide '-e auto_reboot=true' as an extra variable to include these tasks.  

Playbook can be run via ansible-navigator or ansible-playbook.  The inventory should contain all hosts which need to be patched.
The installation inventory is suitable. 

Example: 
```
ansible-navigator run patch_os.yml -i ~/setup/inventory -e auto_reboot=true -e aap_version=2.1
```
or
```
ansible-playbook patch_os.yml -i ~/setup/inventory -e auto_reboot=true -e aap_version=2.1
```
