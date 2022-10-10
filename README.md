# PDK-skywater130
## Inverter
Physical verification using skywater130nm technology


Tools Installation and basic DRC/LVS design Flow:
1. Magic : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/c87742eb5c86f92d0cf546e4f4688c3dec49522f/Images/magic.png"  width="600" height="300">
2. Netgen :

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/4f1a5a8870308362b07e96d650d4b5f52df8c3ed/Images/netgen.png"  width="600" height="300">
3. xschem : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/4f1a5a8870308362b07e96d650d4b5f52df8c3ed/Images/xschem.png"  width="600" height="300">
4. ngspice : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/4f1a5a8870308362b07e96d650d4b5f52df8c3ed/Images/ngspice.png"  width="600" height="300">


## Creating Sky130 device layout in magic: 

Setup commands : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/8dd90a986403240e2b4347749cebed52c4e35ea5/Images/magic_layout_install.png"  width="600" height="300">

```
ln -s /usr/share/pdk/sky130A/libs.tech/xschem/xschemrc
ln -s /usr/share/pdk/sky130A/libs.tech/ngspice/spinit .spiceinit
ln -s /usr/share/pdk/sky130A/libs.tech/magic/sky130A.magicrc .magicrc

```
Now test the setups :
### 1. xschem
```
cd ../xschem
xschem
```

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/0c2a3bda458b0825ae1228220955afd5b8ba7fac/Images/xschem-1.png"  width="600" height="300">
 This has lot of example schematics and it introduces you to sky130 devices.
 
 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/c5b8c11ef01582914f121c9ed541d8faf269be76/Images/schematic-e4.png"  width="600" height="300">

 e4 -> enter into specific block
 
 ctrl + e -> exit
 
 ### 2. magic
```
cd ../mag
magic
magic -d XR (enhanced)
```

## Creating Simple schematic in xschem: 

```
cd ../xschem
xschem
```
Go to file -> new schematic (ctrl+n)

Press *insert* key on keyboard

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/6423d733295cb202270566e47e0571ae4e31ea22/Images/xschem-insert.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/a0dce13cad63102be73b804d27b52b0aa84f2b3c/Images/xschem-insert(1).png"  width="600" height="300">

Select nfet_01v8.sym

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/a0dce13cad63102be73b804d27b52b0aa84f2b3c/Images/xschem-insert(2).png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/a0dce13cad63102be73b804d27b52b0aa84f2b3c/Images/xschem-insert(3).png"  width="600" height="300">

Select pfet3_01v8.sym

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/a0dce13cad63102be73b804d27b52b0aa84f2b3c/Images/xschem-insert(4).png"  width="600" height="300">

Now go back to library and select devices :
### Some useful commands: 
1. If you want to move nfet or pfet press m keyword.
2. If you want to copy press c.
3. delete key to delete component.
4. w key to wire up as shown in diagram below

We need to select 4 : 
1. ipin.sym
2. opin.sym
3. iopin.sym (2)

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/23d10d7a80df9704fa03aeb5b3f6c09a20a9dd84/Images/xschem-9.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/23d10d7a80df9704fa03aeb5b3f6c09a20a9dd84/Images/xschem-8.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/23d10d7a80df9704fa03aeb5b3f6c09a20a9dd84/Images/xschem-7.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/4eafef687bb5031b4a30e7fc8711e9222d0756f1/Images/xschem-6.png"  width="600" height="300">

Now we need to change values of nfet and pfet for the inverter 
Press right click on nfet
### For nfet
<img src="https://github.com/yuganshjain/PDK-skywater130/blob/d4e4e35ca9ebf71dadd0dd556eb029d3e2fdb42a/Images/nfet.png"  width="600" height="300">

### For pfet
<img src="https://github.com/yuganshjain/PDK-skywater130/blob/d4e4e35ca9ebf71dadd0dd556eb029d3e2fdb42a/Images/pfet.png"  width="600" height="300">
