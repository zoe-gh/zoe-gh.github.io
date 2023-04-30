---
title: "Image Hosting with Github & PicGo"
last_modified_at: 2022-06-09
categories: 
- Tools
tags: 
- Website
toc: true
---

## Download PicGo

[PicGo](https://github.com/Molunerfinn/PicGo/releases) is an open source picture bed uploading and management tool.

Image bed supported by PicGo:
- Qiniu Img 
- Tencent Cloud COS 
- Upyun 
- GitHub 
- SM.MS V2 
- Alibaba OSS 
- Imgur 

## Set Github

See [PicGo Guidelines](https://picgo.github.io/PicGo-Doc/en/guide/config.html#github-img)
Create a new repository to store your uploaded images.
Generate a new token at Setting/Developer settings.
Input `repo name`, `branch`, and `token` at PicGo Image Hosting Service Setting.

## Customize Image URL

Default URL has no format.
Set default image format by customize image URL:
 `<img src="$url" width="300" height="">`

## Upload Image and Generate URL

Drag image to PicGo upload area.
Or use shortcut `Ctrl + Shift + P` to upload image from clipboard (shortcut can be customized).
Then past URL to your md files.
