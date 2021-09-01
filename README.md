 ansible role rtl_nic_firmware
===============================

Ansible role to deploy ``rtl_nic`` Firmware for APU.

This role is only running at:
```yaml
when:
  - ansible_board_name == 'APU'
  - ansible_product_name == 'APU'
```

It will download the defined Firmware Files from the ``rtl_nic__firmware`` variable.
Then we run ``update-initramfs -k all -u``.

You can change the downloaded firmware file names by modifying the default variables.
