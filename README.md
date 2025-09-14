# ALfG(Nvidia)
Arch Linux for Gaming
# Before installation
Uncomment multilib in ```/etc/pacman.conf```
```
sudo nano /etc/pacman.conf
```
# Manual
### Install the drivers with the command:
```
sudo pacman -S nvidia nvidia-utils nvidia-settings lib32-nvidia-utils
```
### Power Management:

#### CPU:

1.Install cpupower
```
sudo pacman -S cpupower
sudo systemctl enable cpupower.service
```
2.In the ```/etc/default/cpupower``` file, specify: ```governor='performance'```
```
sudo nano /etc/default/cpupower
```

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
To install proton-ge use yay or paru
```
yay -S proton-ge-custom-bin
```
```
paru -S proton-ge-custom-bin
```
In the steam compatibility settings, select Proton-GE
In the properties of the steam games, enter: ```gamemoderun %command%```
### ZRAM:
1.Install zram-generator:`
```
sudo pacman -S zram-generator
```
2.Configure the zram-generator:
```
sudo nano /etc/systemd/zram-generator.conf
```
3.Paste it into the file:
```
[zram0]
zram-size = min(ram / 2, 4096)
compression-algorithm = zstd
swap-priority = 100
```
### Optional:
Disabling unnecessary services
```
sudo systemctl disable avahi-daemon.service
```
### Reboot your PC after settings 
# Warning

Tested on Nvidia Geforce GTX 1660 SUPER
