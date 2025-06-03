# ALfG
Arch Linux for Gaming
# Before installation

# Manual
for
## Nvidia
### Install the drivers with the command:
```
sudo pacman -S nvidia nvidia-utils nvidia-settings lib32-nvidia-utils
```
### Enable Nvidia DRM:

1.
```
sudo nano /etc/default/grub
```
2. Add it to the first lines: ```GRUB_CMDLINE_LINUX_DEFAULT="... nvidia_drm.modeset=1"```

### Installing the Zen Core:
```
sudo pacman -S linux-zen linux-zen-headers
```

### Power Management:

#### CPU:

1.
```
sudo pacman -S cpupower
sudo systemctl enable cpupower.service
```
2.In the /etc/default/cpu power file, specify: ```#governor='performance'```

#### GPU:
```
sudo nvidia-smi -pm 1
sudo nvidia-smi -pl 125
```
### Game Optimization(steam):
Installing steam and components:
```
sudo pacman -S steam gamemode lib32-gamemode
```
Optional:
```
sudo systemctl disable bluetooth.service avahi-daemon.service
```
### Warning
Tested on Nvidia Geforce GTX 1660 SUPER
## AMD
soon
