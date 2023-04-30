---
title: "VBA Basics"
last_modified_at: 2022-06-15
categories: 
- CS
tags: 
- VBA
toc: true
---

## Setting

- Turn on developer mode
	- Options - Customize ribbon - Developer
- Security
	- Options - Trust center - Trust center setting - Trusted locations & Macro settings
- Save excel with vba
	- Save as *.xlsm
- Open VBE editor
	- From ribbon
	- From right click
	- `Alt + F11`
- Run vba code
	- Run button or `F5`
	- Can add short key for module
	- Can run by button: Developer - Insert

## Basics

- Modular
	- Declaration
	- Procedure
		- Sub: perform a task, not return value
		- Function: return a single value
- Object
	- Excel > Application > Workbook > Range/PivotTable
	- Objects have properties & methods
		- `Range("A1").Value`
		- `Worksheets("Sheet1").Activate`
		- `Range("A1").Copy Range("B1")`
		- `Range("A1").Copy Destination:=Range("B1")`
	- Specify object location
		- `Application.Workbook("Book1.xlsx").Worksheets("Sheet1").Range("A1")`
	- Collection
		- e.g. Workbooks, Worksheets, Charts, Sheets
		- Worksheets(1)
			- First Worksheet in Worksheets collection
- Naming
	- No reserved words
	- No space, period
	- No distinguish between uppercase and lowerase
	- Descriptive names
- Macro record
	- Can choose absolute or relative in Developer - Use realtive reference
- Line continuation character: underscore `_`
- Comment: `'comment`

### Elements

- Data type

  <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220610103358.png" width="600" height="">

- `Option Explicit`: must declare all variables to run module
- `Ctrl + space` to ambiguous search variable names
- Declare variable data type (can only one variable one statement)
	- Procedure-only vairable: Dim/Static
		- Static is static variable, unchangeable
	- Module-only variable: Dim/Private
	- Public variable: Public
- Const: constant
- String
	- `Dim MyString As String * 50` to specify max length of string
- Date
		- `Const FirstDay As Date = #mm/dd/yyyy#`
		- `Const Noon = #12:00:00#`
- Arthmetic operator:

  <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220613103007.png" width="500" height="">

- Logical operator:

  <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220613103147.png" width="500" height="">

- Array
	- One-dimensional array
		- `Dim MyArray (0 To 100) As Integer`
		- `Dim MyArray (100) As Integer`
			- VBA assumes the lower index as 0
			- `Option Base 1` to set default lower index
	- Multi-deimensional array
		- `Dim MyArray (0 To 9, 0 To 9, 0 To 9) As Integer`
		- `MyArray (3, 4, 0) = 125` to specify element by index numbers
	- Dynamic array
		- `Dim MyArray () As Integer`
		- `ReDim MyArray (1 to NumElements)` to specify number of elements later
			- Originally stored values are wiped out
			- `ReDim Preserve MyArray (1 to NumElements)` to preserve originial values
- Label
	- `040:` must be in the beginning of a line


### Range

- `Range(PriceList)` to call range with defined name
- `Range("A1:B8, K3, 9:9")`
- Cells property
	- Refer to a cell
	- `Range("A1:H10").Value = 99`
	- `Range(Cells(1,1), Cells(10,8)).Value = 99`
- Offset property
	- Refer to a cell rows (below) and cols (right) away from another cell
	- `ActiveCell.Offset(1,-2) = Time`
- Value property
	- Read-write property
- Text property
	- Return a string of displayed text
- Count property
	- Read-only property
	- Including blank cells
- Column and Row property
	- Num of cols and rows of a single-cell range
	- If Range consists of more than one cell, only return the first one
- Address property
	- Read-only property
	- Return absolute reference for a range
- HasFormula property
	- Read-only property
	- Return TRUE if all cells contain a formula
	- Return FALSE if all cells do not contain a formula
	- Return NULL if mix
		- NULL is not a boolean
		~~~
			Sub CheckForFormulas()
				Dim FOrmulasTest As Variant
				FormulaTest = Range("A1:A2").HasFormula
				If TypeName(FormulasTest) = "Null" Then
					MsgBox "Mixed"
				Else
					MsgBox FormulaTest
				End If
			End Sub
		~~~
- Font property
		- `Range("A1").Font.Bold = True`
- Interior property
	- `Range("A1").Interior.Color = Int(16777216 * Rnd)` to change cell bg color to random
	- `Range("A1").Interior.Color = RGB(255,0,0)`
	- `Range("A1").Interior.Color = vbRed`
- Formula property
	- Read-write property
	- `Range("A12").Formula = "=SUM(A1:A11)&"" nos"""`
- NumberFormat property
	- Read-write property
	- `Columns("A:A").NumberFormat = "0.00%"`
- Select method
	- Sheet need to be activated before other method
	~~~
	Sheets("Sheet1").Activate
	Range("A1:C12").Select
	~~~
- Copy and Past method
	~~~
	Sub CopyRange()
		Range("A1:A12").Select
		Selection.Copy
		Range("C1").Select
		ActiveSheet.Paste
	~~~
	~~~
	Sub CopyRange()
		Range("A1:A12").Copy Range("C1")
	End Sub
	~~~
- Clear method
	- Delete the content of a range
	- ClearContents: leave format
	- ClearFormats: leave contents
- Delete method	
	- Delete and shift remainning cells around to fillup the deleted range
	- `Range("A1:C3").Delete xlToLeft`

## Function

- Function sources
	- Built-in VBA function
	- Worksheet Excel function
	- Custom function using VBA

- Built-in VBA funtion

	<img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220616184017.png" width="600" height="">
	<img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220616184053.png" width="600" height="">
	<img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220616184232.png" width="600" height="">
	<img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220616184135.png" width="600" height="">
	<img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220616184153.png" width="600" height="">

- Use worksheet function in VBA
	- WorksheetFunction (object under Application)
	~~~
	Total = Application.WorksheetFunction.SUM(Range("A1:A12")) 
	Total = WorksheetFunction.SUM(Range("A1:A12")) 
	Total = Application.SUM(Range("A1:A12"))
	~~~

## VBA Application

### Decrypt Protected Excel

VBA module and run:

~~~
Sub DeletePW()
ActiveSheet.Protect DrawingObjects:=True, Contents:=True, AllowFiltering:=True
ActiveSheet.Protect DrawingObjects:=False, Contents:=True, AllowFiltering:=True
ActiveSheet.Protect DrawingObjects:=True, Contents:=True, AllowFiltering:=True
ActiveSheet.Protect DrawingObjects:=False, Contents:=True, AllowFiltering:=True
ActiveSheet.Unprotect
End Sub
~~~

