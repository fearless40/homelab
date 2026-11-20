
Simplified Commands

With ansible.cfg in place, Ansible automatically picks up inventory/hosts.yml and roles/ whenever you run commands from the project root:
• Provision the full stack:bash
ansible-playbook site.yml

• Update only DNS or DHCP:bash
ansible-playbook site.yml --tags dns

• Teardown a single VM:bash
ansible-playbook teardown.yml -e removevm_confirm=true -e target_vm=web-02

• Verify inventory parsing:bash
ansible-inventory --graph

(Security Note: Make sure your project directory is not world-writable, as Ansible intentionally ignores ansible.cfg inside world-writable directories (777) to prevent untrusted configuration injection.)
