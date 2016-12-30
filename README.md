Ansible irssi Role
==================

An ansible role for installing and configuring irssi

Role Variables
--------------

```yaml
irssi_packages: list of packages and plugins that you want to install
irssi_config_directories: nested dictionary list with all directories needed to put configuration files. Also holds path, permissions, etc
  - owner: michael
    group: michael
    base_path: /home/michael
    directories:
      - name: .irssi
        mode: '0700'
      - name: .irssi/otr
        mode: '0700'
      - name: .irssi/scripts
        mode: '0755'
      - name: .irssi/scripts/autorun
        mode: '0755'
irssi_config_files: nested dictionary list with all configuration files. Also holds path, permissions, etc
  - owner: michael
    group: michael
    base_path: /home/michael/.irssi
    files:
      - name: default.theme
        mode: '0640'
      - name: config
        mode: '0640'
      - name: screen
        mode: '0700'
      - name: otr/otr.fp
        mode: '0600'
      - name: otr/otr.key
        mode: '0600'
      - name: scripts/screen_away.pl
        mode: '0664'
      - name: scripts/fnotify.pl
        mode: '0644'
irssi_autorun_files: dictionary
  - base_path: /home/michael/.irssi/scripts
    files:
      - screen_away.pl
      - fnotify.pl
```

Example Playbook
-------------------------

```yaml
    - hosts: servers
      roles:
         - { role: MichaelRigart.irssi, become: true }
```

License
-------

GPLv3

Author Information
------------------

Michaël Rigart <michael@netronix.be>
