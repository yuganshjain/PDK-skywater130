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
 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/089312c278af7ac0213419870002a5a9efbe0bd3/GDS_images/gds_1_1.png"  width="600" height="300">
After the console :

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/089312c278af7ac0213419870002a5a9efbe0bd3/GDS_images/gds_1_2.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/089312c278af7ac0213419870002a5a9efbe0bd3/GDS_images/gds_1_3.png"  width="600" height="300">

```
gds read /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/gds/sky130_fd_sc_hd.gds
cellname top

```
Go to cell manager -> will get a scrollable list 

and select and_2_1


<img src="https://github.com/yuganshjain/PDK-skywater130/blob/089312c278af7ac0213419870002a5a9efbe0bd3/GDS_images/gds_1_4.png"  width="600" height="300">

now back in terminal write
```
cif istyle sky130(vendor)
gds read /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/gds/sky130_fd_sc_hd.gds
```
<img src="https://github.com/yuganshjain/PDK-skywater130/blob/089312c278af7ac0213419870002a5a9efbe0bd3/GDS_images/gds_1_5.png"  width="600" height="300">

## 2. Ports
in tkcon terminal
```
port index
port first
lef read /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/lef/sky130_fd_sc_hd.lef
port 1 name
readspice /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/spice/sky130_fd_sc_hd.spice

```



<img src="https://github.com/yuganshjain/PDK-skywater130/blob/330c9236b125f0e37d1dbf8e7a0079eedbc13078/GDS_images/gds_2_1.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/330c9236b125f0e37d1dbf8e7a0079eedbc13078/GDS_images/gds_2_2.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/330c9236b125f0e37d1dbf8e7a0079eedbc13078/GDS_images/gds_2_3.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/330c9236b125f0e37d1dbf8e7a0079eedbc13078/GDS_images/gds_2_4.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/330c9236b125f0e37d1dbf8e7a0079eedbc13078/GDS_images/gds_2_5.png"  width="600" height="300">
