# RH-294
Sample Question and Answer


- name: installing mariadb
  yum:
    name: "{{ soft1 }}"
    state: present

  when: inventory_hostname in groups['dev']

- name: installing vsftpd and php
  yum:
          name: "{{ item }}"
          state: present
  loop: "{{ soft2 }}"
  when: inventory_hostname in groups['prod']
