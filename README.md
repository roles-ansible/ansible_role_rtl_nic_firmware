[![Galaxy](https://github.com/roles-ansible/ansible_role_rtl_nic_firmware/raw/main/.github/galaxy.svg)](https://galaxy.ansible.com/do1jlr/rtl_nic_firmware)
[![License](https://github.com/roles-ansible/ansible_role_rtl_nic_firmware/raw/main/.github/license.svg)](https://github.com/roles-ansible/ansible_role_rtl_nic_firmware/blob/main/LICENSE)

 ansible role rtl_nic_firmware
===============================

Ansible role to install some missing ``rtl_nic`` Firmware for APU.

This role is only running at:
```yaml
when:
  - ansible_board_name == 'APU'
  - ansible_product_name == 'APU'
```

+ It will download the defined Firmware Files from the ``rtl_nic__firmware`` variable.
+ Then we run ``update-initramfs -k all -u``.

You can change the downloaded firmware file names by modifying the default variables.

Optionally you can perform a simple versionscheck, that can prevent you from running a older version of this role accidentially.

 Variables
-----------
```yaml
---
# define download url prefix
rtl_nic__download_prefix: 'https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/plain'

# defined firmware list
rtl_nic__firmware:
  - 'rtl_nic/rtl8107e-2.fw'
  - 'rtl_nic/rtl8107e-1.fw'
  - 'rtl_nic/rtl8168h-2.fw'
  - 'rtl_nic/rtl8168h-1.fw'
  - 'rtl_nic/rtl8168g-3.fw'
  - 'rtl_nic/rtl8168g-2.fw'
  - 'rtl_nic/rtl8106e-2.fw'
  - 'rtl_nic/rtl8106e-1.fw'
  - 'rtl_nic/rtl8411-2.fw'
  - 'rtl_nic/rtl8411-1.fw'
  - 'rtl_nic/rtl8402-1.fw'
  - 'rtl_nic/rtl8168f-2.fw'
  - 'rtl_nic/rtl8168f-1.fw'
  - 'rtl_nic/rtl8105e-1.fw'
  - 'rtl_nic/rtl8168e-3.fw'
  - 'rtl_nic/rtl8168e-2.fw'
  - 'rtl_nic/rtl8168e-1.fw'
  - 'rtl_nic/rtl8168d-2.fw'
  - 'rtl_nic/rtl8168d-1.fw'

rtl_nic__path_prefix: '/lib/firmware'
rtl_nic__path_suffix: 'rtl_nic'

# should we do a version check? (true is recomended)
submodules_versioncheck: false
```
