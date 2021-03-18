# windows_update
This repo contains an Ansible role that updates Windows systems. This role mainly utilizes the win_update module, in
addition to that it provides retry capability for older OSes with many updates pending such as Windows 2008 R2 and
Windows 7. It also reports on installed updates.

> **_Note:_** This role is provided as an example only. Do not use this in production. You can fork/clone and add/remove steps for your environment based on your organization's security and operational requirements.

Requirements
------------

Role Variables
--------------

Dependencies
------------

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: update windows systems
      hosts: all
      gather_facts: True
      become: no
      vars:
        win_update_category_names:
          - CriticalUpdates
          - DefinitionUpdates
          - SecurityUpdates
          - UpdateRollups
          - Updates
            
      roles:
        - oatakan.windows_update

For disconnected environments, you can overwrite this variable to point to a local copy of a script to enable winrm:

**winrm_enable_script_url:** https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1

you can also localize virtio-win and update the virtio_iso_url variable to point to your local url:

**virtio_iso_url:** https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/archive-virtio/virtio-win-0.1.173-2/virtio-win.iso

License
-------

MIT

Author Information
------------------

Orcun Atakan
