# AutoYaST Profiles for openSUSE Leap

The [AutoYaST](https://doc.opensuse.org/documentation/leap/autoyast/html/book-autoyast/index.html) profiles in this repository are for automating a clean installation of [openSUSE Leap](https://www.opensuse.org/#Leap).
They are not intended to be used *as is* by anyone except myself.

## Installation

Boot the machine from the openSUSE Leap installation media.
At the boot screen, make sure **Installation** is selected and press the `E` key to edit the installation entry.
Add the following space-separated parameters to the end of the line that starts with `linux` or `linuxefi`:

```
 ifcfg=eth0=dhcp autoyast=https://raw.githubusercontent.com/serock/autoyast-profiles/main/autoinst.erb
```

Press the `F10` key to continue the installation.

## Post Installation

Edit `/etc/ddclient.conf` to set the `login` and `password`.

```
sudo vi /etc/ddclient.conf
```

Enable and start the `ddclient` service.

```
sudo systemctl --now enable ddclient.service
```
