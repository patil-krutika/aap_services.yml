# aap_services.yml
---
- name: checking service status
  hosts: localhost
  tasks:
  - name: checking service status
    command: systemctl status "{{ item }}"
    with_items:
    - automation-controller
    - nginx
    - supervisord
    - postgresql
    - redis
    register: result
    ignore_errors: yes
  - name: showing report
    debug:
     var: result

