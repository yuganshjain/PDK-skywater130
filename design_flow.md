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


## Creating Symbol and exporting schematic in xschem: 
1. Go to symbols
2. Make symbols from schematic
New schematic -> library -> open inverter.sym -> click ok

Now insert devices/vsource.sym
insert gnd.sym

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/11f46ecb276c7b8db58957af9400428980986dd9/Images/symbol-1.png"  width="600" height="300">

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/11f46ecb276c7b8db58957af9400428980986dd9/Images/symbol-2.png"  width="600" height="300">
 
 Create pins for signals in ngspice output
 opin.sym
 Connect as shown and change in out name.
 Now change voltages 

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/c1d35581b4a80fb00404234b302d7f9af58eb550/Images/symbol-3.png"  width="600" height="300">

insert devices/codeshown.sym
and change 1st blabla value to value = ".lib /usr/share/pdk/sky130A/libs.tech/ngspice/sky130.lib.spice tt"
and 2nd codeshown value to value = ".control
tran 1n 1u
plot V(in) V(out)
.endc"

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/5100fbef92c0c77656c79eaba64b7a37bf69f4d0/Images/symbol-4.png"  width="600" height="300">


Now save file as inverter_tb.sch

After this click on netlist and then simulation
It will display plot of input vs output

<img src="https://github.com/yuganshjain/PDK-skywater130/blob/a4ed01374c49c163da5cfa82abaa4f1aad189203/Images/symbol-5.png"  width="600" height="300">

Now the circuit is functionally validated through simulation, now we are ready for layout


Now file -> open -> inverter.sch -> click ok

Now Go to simulation  -> LVS netlist checked.
Click on netlist
and then quit.
That's all for xschem.


## Importing Schematic To Layout and Inverter Layout Steps

```
cd ../mag
magic -d XR
```

Go to file 
Import spice
Go to xchem -> open inverter.spice


<img src="https://github.com/yuganshjain/PDK-skywater130/blob/1a93acb2b290d9ede01de5e64d26c42cccd6cc18/Images/spice-1.png"  width="600" height="300">

V key press to get full view


<img src="https://github.com/yuganshjain/PDK-skywater130/blob/1a93acb2b290d9ede01de5e64d26c42cccd6cc18/Images/spice-2.png"  width="600" height="300">

**i to select the block and m to move it and s to select below blocks**
i and then ctrl+p (paramaters) 
for pfet
select top guard ring via coverage and type 100.
source via coverage = 40
drain via coverage = -40

for nfet
bottom guard ring via coverage = 100
source via covergae = +40
drain via coverage = -40


<img src="https://github.com/yuganshjain/PDK-skywater130/blob/f9fc8233ffdde9d57c2648cc9d4c674cedf52ecf/Images/1.png"  width="600" height="300">

```
extract do local
extract all
ext2spcie lvs
ext2spice
quit
```
<img src="https://github.com/yuganshjain/PDK-skywater130/blob/f9fc8233ffdde9d57c2648cc9d4c674cedf52ecf/Images/2.png"  width="600" height="300">

now 

```
cd ../netgen
netgen -batch lvs "../mag/inverter.spice inverter" "../xschem/inverter.spice inverter"
```
<img src="https://github.com/yuganshjain/PDK-skywater130/blob/f9fc8233ffdde9d57c2648cc9d4c674cedf52ecf/Images/3.png"  width="600" height="300">
