# fedora-config

# remove unused packages

```
sudo dnf remove firefox libreoffice*
sudo dnf autoremove
```

# make dnf faster

```
sudo nano /etc/dnf/dnf.conf
```

Add these lines:

```
max_parallel_downloads=10
fastestmirror=True
```

Save and exit.

# system update

```
sudo dnf update --refresh
```

reboot

# intel undervolt

```
sudo dnf install intel-undervolt
sudo nano /etc/intel-undervolt.conf
```

Change undervolt values:

```
undervolt 0 'CPU' -135
undervolt 1 'GPU' -135
undervolt 2 'CPU Cache' -135
undervolt 3 'System Agent' 0
undervolt 4 'Analog I/O' 0
```

Save and exit.

```
sudo intel-undervolt apply
```

To make changes persistent across reboots:

```
sudo systemctl enable intel-undervolt.service
```

# add zsh with ohmyzsh as default terminal

zsh

```
sudo dnf install zsh
```

ohmyzsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

change default shell to zsh

```
chsh -s $(which zsh)
```

reboot
