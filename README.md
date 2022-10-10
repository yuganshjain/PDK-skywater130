# PDK-skywater130
Physical verification using skywater130nm technology

DAY:1 
Tools Installation and basic DRC/LVS design Flow:
1. Magic : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/c87742eb5c86f92d0cf546e4f4688c3dec49522f/Images/magic.png"  width="600" height="300">
2. Netgen :

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/4f1a5a8870308362b07e96d650d4b5f52df8c3ed/Images/netgen.png"  width="600" height="300">
3. xschem : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/4f1a5a8870308362b07e96d650d4b5f52df8c3ed/Images/xschem.png"  width="600" height="300">
4. ngspice : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/4f1a5a8870308362b07e96d650d4b5f52df8c3ed/Images/ngspice.png"  width="600" height="300">


##Creating Sky130 device layout in magic: 

Setup commands : 

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/8dd90a986403240e2b4347749cebed52c4e35ea5/Images/magic_layout_install.png"  width="600" height="300">

```
ln -s /usr/share/pdk/sky130A/libs.tech/xschem/xschemrc
ln -s /usr/share/pdk/sky130A/libs.tech/ngspice/spinit .spiceinit
ln -s /usr/share/pdk/sky130A/libs.tech/magic/sky130A.magicrc .magicrc

```
Now test the setups :
```
cd ../xschem
xschem
```

 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/0c2a3bda458b0825ae1228220955afd5b8ba7fac/Images/xschem-1.png"  width="600" height="300">
 This has lot of example schematics and it introduces you to sky130 devices.
 
 <img src="https://github.com/yuganshjain/PDK-skywater130/blob/c5b8c11ef01582914f121c9ed541d8faf269be76/Images/schematic-e4.png"  width="600" height="300">

 e4 -> enter into specific block
 
 ctrl + e -> exit
 
```
cd ../mag
magic
```
