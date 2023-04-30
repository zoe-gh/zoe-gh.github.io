---
title: "AutoCAD Basics"
last_modified_at: 2022-06-15
categories: 
- Tools
tags: 
- AutoCAD
toc: true
---

## Settings

- Unit
	- `A -> drawing utilities` or `UN`
- Manubar
- Option
	- `tools -> options` or `OP` 
	- files
		- automatic save file location
	- display 
		- colors - black and white
		- display paper background x
		- display paper shadow x
		- crosshair size - max or u like
	- open and save
		- save as - lower version
		- auto save - 10/15 min
	- user preferences
		- associative dimensioning x
	- drafting & selection
	- 3d modelling
		- show z axis x
	- selection
		- pickbox size & grip size
- Object snap
	- `tools -> draft setting` or `OS`
	- all except geometic center
	- dynamic input
		- enable pointer input v
- grid line
	- F7 to hide and show

## Basics

- `ctrl + s` to save
- `ctrl + z` or `U` to undo
- `ctrl + y` to redo
- `space`
	- confirm
	- repeat last command
- `esc`
	- cancel
- view
	- `wheel`
		- pan (hold) 
		- zoom (scroll)
	- `Z` for zoom
		- `Z + A` = double click scroll
	- `P` for pan
- select
	- click selection
	- frame selection
		- from left: enclosed items
		- from right: crossed items
- `F8` Ortho mode
- `RE`generate = refresh
- `U`ndo = `Ctrl + Z`
- `PDFI`mport: pdf import to cad
- `shift + space` = switch to select overlapped objects

## Draw

- `L`ine: line
	- click for first point or type in the Cartesian coordinates 0,0
- `XL`ine: construction line
	- infinite length
- `PL`ine: polyline
	- `W`idth to set begin and end width
- `ML`ine: multiline
	- `J`justification: direction of additional line
	- `S`cale: overal width
- `SPL`ine: spline
	- smooth curve like pen tool in PS
- `POL`ygon: polygon
- `REC`tangle: rectangle
	- `C`hamfer: recessed edge
	- `F`illet: round edge
- `A`rc: arch
- `C`ircle: circle
- `REVC`loud: review cloud
- `EL`lipse: ellipse
- `I`nsert: insert block
- `ER`: external reference
	- Insert image or dwg
- `B`lock: block
	- pick base point
	- allow exploding
	- redefine block by using same name to create block or edit block definition by double click
- `G`roup: group
	- group disappers after `UNGROUP`
- `PO`int: point
	- Format - point style
- `H`atch: hatch
	- select (line) or select point
	- pattern scale
	- `GRA`: gradient
	- delete boundary, drag, right click, generate boundary
- `BO`undary & `REG`ion" boundary
	- generate group lines
	- `BO` 
		- original non-grouped lines reserved
		- drag grouped line point deform shape
		- just use this
	- `REG` 
		- original non-grouped lines not reserved
		- drag grouped line point to move whole region
- `T`ext & `DT` & `ATT`: text
	- `T` for single line
	- `DT` for multi lines
	- `ATT` for text attributes
		- select only preset
		- can change attribute value after forming block
	- Align: property - justify or right click after `TEXT`
- `W`rite: write block to export block as file
- `DIV` & `ME`: divide & measure
	- `DIV` to input number of segment
	- `ME` to input length of segment
	- `B` to insert block at equal intervals
		- alignment ref to block base point
- `DO`nut: donut
- `WIPE`out: wipeout
	- to cover certain area by a polygon frame
	- set draw order by right click

## Edit

- `E`rase: erase
- `M`ove: move
- `CO`py: copy
- `OF`fset: offset
- `AR`ray
	- `ARRAYCLASSIC` can edit single object in array
- `MI`rror: mirror
- `RO`tate: rotate
	- counterclockwise
- `SC`ale: scale
	- can insert calculation
	- `R`eference
- `S`tretch: stretch
	- right frame select points to stretch
- `TR`im: trim
	- drag
- `EX`tend: extend
	- select end object, `EX`, drag to select extended lines
- `BR`eak: break
	- `F` for first point
- `J`oin: joint
	- group lines
- `CHA`mfer: chamfer
	- `D`istance
	- `A`ngel
- `F`illet: fillet
	- `R`adius
- e`X`plode" explode block
- `ED`it: edit text
- `PU`rge: purge unused items

## Property, layer and view

- `MO` = `Ctrl + 1`: property
	- `MA`: match property format
	- Property
		- by layer
		- by blcok
	- Linetype can be scaled
	- CAD color selector plugin
- `LA`yer: layer
	- Naming: Index + Description
	- Existing/new work
	- Annotate & text
	- Each layer with differnet color
	- Layer template
		- Create lines for each layer
		- Copy and past lines to new drawing to set layers
		- Layers will not be purged
	- Hide & freeze
		-	Hide in model
		-	Freeze
		-	Hide in model view
		-	Hide in print
		-	<img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220618000456.png" width="100" height="">
- View
	- `MV`: model view in layout
	- `MS`pace & `PS`pace to go in modle view or layout view
	-	Scale
	- `MO` property to change model view scale
	- Or `Z`oom - `S`cale - 1/nxp
	- Or the trangle of model view (not recommend)
	- Display lock - yes

## Annotate

- `D`: Dimension style manager - to create style
	- Name style `1：n`
	- Lines
		- Color 44 *2
		- Extend beyond dim lines 2
		- Offeset from origin 2
		- Fixed length extension lines 5
	- Symbols and arrows
		- Architectural tick *2
		- Arrow size 1
	- Text
		- Color Yellow
		- Text height 2
		- Offset from dim line 0.6
	- Fit
		- Always keep text between ext lines
		- Over dimension line, without leader
		- Use overall scale of n
	- Primary units
		- Precision 0
- Basic dimension
	- `DLI`: dimension linear
	- `DAL`: dimension aligned
	- `DRA`: dimension radius
	- `DDI`: demension diameter
	- `DAN`: dimension angualr
	- `DCE`: dimension center
- `DCO`: dimension continue
	- Repeat last dimension acion
- `DIMBASELINE`: continued dimension according to baseline
- `QDIM`: quick dimension
- Eidt dimension format
	- `DIMBREAK`: break dimension
	- `DIMSPACE`: adjust dimensions space
- `MLD` MLEADER: multileader
	- Add leader for multiple arrows



