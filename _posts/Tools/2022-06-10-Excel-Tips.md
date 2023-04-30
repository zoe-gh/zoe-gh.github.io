---
title: "Excel Tips"
last_modified_at: 2022-06-15
categories: 
- Tools
tags: 
- Excel
toc: true
---

## Shortcut

- Edit cell `F2`
- Switch sheet `Ctrl + PgUp / PgDn`

## Quick hide and unhide in group

- Data -> Group

## Bath create folders

- Format in excel
    - `md folder\folder`
- Copy and paste to `.txt`
- Rename `.txt` to `.bat`

## Combine & apart string in field

- Replace characters in string
    - `SUBSTITUTE(text, old_text, new_text, [instance_num])`
- Find index number of first character in a string
    - `FIND(find_text, within_text, [start_num])`
    - If want to find the second character, use find() for within_text
- Get the length of string
    - `LEN(text)`
- Get left/right part of string
    - `LEFT(text, [num_chars])`
    - `RIGHT(text, [num_chars])`
- Get middle part of string 
    - `MID(text, start_num, num_chars)`
- Combine string
    - `&`: e.g. `=A1&" "&A2`
    - `CONCAT(text1, [text2],…)`