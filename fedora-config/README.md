# fedora-config

# removing unused packages

```
sudo dnf remove firefox libreoffice*
sudo dnf autoremove
```

# making dnf faster

```
sudo nano /etc/dnf/dnf.conf
```

Add these lines:

```
max_parallel_downloads=10
fastestmirror=True
```

`Save and exit.`

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

`Save and exit.`

```
sudo intel-undervolt apply
```

To make changes persistent across reboots:

```
sudo systemctl enable intel-undervolt.service
```

# system update

```
sudo dnf update --refresh
```
