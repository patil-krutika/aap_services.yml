# aap_services.yml
---
- name: check status of services
  hosts: 10.3.0.15
  tasks:
    - name: check the services
      command: systemctl status "{{ item }}"
      with_items:
        - redis-server
        - postgresql
