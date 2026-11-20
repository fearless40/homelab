• Run the entire stack (DHCP + DNS + XCP-ng VMs + SSH verification):bash
ansible-playbook -i inventory/hosts.yml site.yml

• Update only DNS records (e.g., after editing bind_static_a_records in hosts.yml):bash
ansible-playbook -i inventory/hosts.yml site.yml --tags dns

• Update only DHCP & DNS without querying XCP-ng:bash
ansible-playbook -i inventory/hosts.yml site.yml --tags network

• Provision VMs only (skipping DHCP/DNS updates):bash
ansible-playbook -i inventory/hosts.yml site.yml --tags vm
