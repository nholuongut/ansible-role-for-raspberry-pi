# Ansible Role: Raspberry Pi

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

Configures a Raspberry Pi (running Raspbian).

This role will reconfigure certain options in the Raspberry Pi configuration files, but will not automatically _restart_ the Pi to make all the changes take effect. For most changes, you'll need to make sure to reboot your Pi(s) after this role runs.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    raspberry_pi_boot_config_options:
      # Set the GPU memory split value.
      - regexp: "^#?gpu_mem"
        line: "gpu_mem=16"
      # Enable 1200ma USB current on newer model Pis.
      - regexp: "^#?max_usb_current"
        line: "max_usb_current=1"

Use Ansible's `lineinfile` module to ensure certain settings are configured inside `/boot/config.txt`.

    raspberry_pi_rc_local_options:
      # Disable HDMI on startup (for power savings).
      - regexp: "^/usr/bin/tvservice"
        line: "/usr/bin/tvservice -o"

Use Ansible's `lineinfile` module to ensure certain settings are configured inside `/etc/rc.local`.

## Dependencies

None.

## Example Playbook

    - hosts: pi
      vars_files:
        - vars/main.yml
      roles:
        - { role: nholuong.raspberry-pi }

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
