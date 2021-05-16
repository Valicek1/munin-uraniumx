# Munin plugins for UraniumX Core

Original code from [infertux/munin-bitcoin](https://github.com/infertux/munin-bitcoin). 

## Installation & Configuration

1. Copy the `uraniumxd_*` scripts to `/etc/munin/plugins`.

1. If you're using SELinux, don't forget to `chcon` them properly.

1. Configure the plugins by creating a file named `/etc/munin/plugin-conf.d/uraniumxd` with this content:

    ```
    [uraniumxd*]
    user uraniumx
    # env.binary /path/to/uraniumx-cli
    # env.data_dir /var/lib/uraniumx
    ```

    This will tell Munin to run `uraniumx-cli` as the `uraniumx` user. Adapt it to your setup and avoid using `root`.

1. Restart the *munin-node* daemon with `systemctl restart munin-node` or `/etc/init.d/munin-node restart`.

1. Done. You should now start to see a new section *uraniumxd* in your Munin pages with the corresponding graphs.

## License

AGPLv3+

