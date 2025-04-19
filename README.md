pve_vm_from_template
=========

This ansible role creates VM from the temaplte in the Proxmox VE.


Requirements
------------

Proxmox VE running on the target host.

Role Variables
--------------

Please check `defaults/main.yml`

Dependencies
------------

No dependencies.

Example Playbook
----------------

```yaml
- name: Example playbook
  hosts: proxmox_servers

  tasks:
    - name: Create VM from template
      include_role: 
        name: pve_vm_from_template
      vars:
        pve_vm_from_template_api_host: "{{ ansible_host }}:8006"
        pve_vm_from_template_api_user: root@pam
        pve_vm_from_template_api_password: changeme
        pve_vm_from_template_name: newvm
        pve_vm_from_template_cores: 1
        pve_vm_from_template_memory: 1024
        pve_vm_from_template_disk: 5G
        pve_vm_from_template_net0_config: dhcp
        pve_vm_from_template_root_password: changeme
        pve_vm_from_template_root_ssh_key_from_proxmox: true
        pve_vm_from_template_add_to_inventory: false
        pve_vm_from_template_inventory_file: "{{ inventory_dir }}/hosts"
        pve_vm_from_template_ansible_group: "vms"
```

License
-------

MIT
