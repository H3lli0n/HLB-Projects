This project open-source, all files to order a batch of pcb-a are free to use. This project is also sponsored by PCBWay. 

PCBWay is an online services to manufacture pcb/pcb-a (pcb with assembly which means all components soldered). 

If you need their services please use the following link to support the team ! https://pcbway.com/g/4Gd3AJ
![PCBWay](PCBWay-logo-new.png)

# Description
- 40% ANSI / ISO
  - Hotswap *HLB40-H*
    - RP2040 MCU
    - Capslock/Layers indicator
  - EC (Electro Capacitive) *HLB40-EC*
    - STM32F MCU
- Bottom row
  - 6U
  - 2.75U/1U/2.25U
- QMK / VIAL firware
  - RGB management under my userspace (HLB40-H)

# Layout

# Files
## HLB40-H
*Files will be available once tested*
## HLB40-EC
*Files will be available once tested*

# How to order
Ordering pcb through PCBWay is straightforward but you can be lost at some points so we will guide you along the process.

## Files
Once you downloaded the pcb version you wan, unzip the archive into a folder. You shall have those files
![Files](tuto/001.png)
- *hlb40_h.kicad_pcb_gerber.zip*: the main file containing all pcb data, layers, routes... Everything the service needs to fill data form
- *hlb40_h.kicad_pcb_bom.csv*: listing of all components to assemble onto the pcb - each component is identified by a code and the service knows exactly what to order
- *hlb40_h.kicad_pcb_positions.csv*: positions of each component on the pcb for assembly

## Creating PCBWay account
The next step is to create an account on PCBWay by following our affiliated link https://pcbway.com/g/4Gd3AJ - once your account created you will receive later a $5 coupon.

## Requesting a quote
Now it's time to order by uploading all files and selecting the right options. One key factor of the final price is the quantity.
Default minimum quantity is 5 and price decreases with higher quantities. Before ordering you can find some friends or others hobbyist on our discord to buy a higher batches !

Ok for this example we will order 5 pcb (the board with copper layers) and request 5 assemblies (components soldered on the pcb).

### PCB Quote menu
Before assembly we have to quote the pcb itself, to do so click on *PCB Instant Quote*

![Step1](tuto/002.jpg)
And *Quick Order*

![Step2](tuto/003.jpg)

Where you can upload the Gerber file from our archive as listed before.
Our PCB is composed of 4 layers so you have to specify their order:
- L1 : F.Cu
- L2 : In1.Cu
- L3 : In2.Cu
- L4 : B.Cu
![Step3](tuto/004.jpg)

You can even have a look on the PCB preview with their *Gerber Online Viewer*
![Step4](tuto/005.jpg)

### Ordering options
#### Quantity
Now we have to check the options and modify some items. As described before, the final price of the order is quantity dependant because manufacturing few items requires the same technical effort than on a large batch. This human cost is divided over the number of item purchased.

![Step5](tuto/006.jpg)
![Step5b](tuto/006b.jpg)

Don't hesitate to make an announcement on our discord maybe you'll find people interested in this order and split the cost.
Also be aware that it might be expensive but PCBWay services is more "human" than others meaning a lot of reviews is done on your request to avoir mistakes.

#### Good looking PCB
Our PCB is 1.6mm thickness and you can custom its color through *Solder mask* option. Here we select a red one (we will type faster for sure!)
![Step6](tuto/007.jpg)

#### Soldering option
Since we live in Europe and we are "eco friendly" please avoir lead that is now banned from our continent.
Thanks to select *HASL lead free* meaning soldering is made from silver paste.
![Step7](tuto/008.jpg)

Note: for solder PCB (not hotswap) you shall select ENIG based option to have strong switches pads.

By default a serial number will be printed on the pcb. You can remove this printing with the option below.
![Step8](tuto/009.jpg)

#### Assembly
Now we are enabling the assembly part of the order. With this step each electronic component will be ordered and soldered. This step is mandatory.
![Step9](tuto/010.jpg)

#### Custom options
This option is not essential but will save some space in the box and avoid to cut soldering panels needed for machines to slide pcb. This option doesn't add much on the final cost.
![Step10](tuto/011.jpg)

You just have to click on *Bottom side* meaning all our components will be soldered on the back.
When done you just have to click on *Save to Cart*
![Step11](tuto/012.jpg)

### Cart
We are almost at the end with two orders in our cart, one for pcb manufacturing and one for assembly.

![Step12](tuto/013.jpg)

As you can see, we have files to upload for the assembly, the two remaining described .csv files earlier.
One for position (*Upload Centroid file* in the form) and one for the list of components (*Parts Lists (BOM) upload*).

![Step13](tuto/014.jpg)

And we are done you can submit your cart that will be reviewed.

![Step14](tuto/015.jpg)

You don't have any extra step to manage, commercial and the whole PCBWay team will manage your uploaded files and solder everything at the correct positions. This is done by the footprints used and all the mandatory marks on the pcb.