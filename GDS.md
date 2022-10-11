# GDS read write, extraction,DRC,LVS and XOR setup

## 1. GDS read
```
mkdir lab
cd lab
mkdir mag
cd mag
cp /usr/share/pdk/sky130A/libs.tech/magic/sky130A.magicrc ./.magicrc
magic -d XR
```
After the console :

```
gds read /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/gds/sky130_fd_sc_hd.gds
cellname top
```
