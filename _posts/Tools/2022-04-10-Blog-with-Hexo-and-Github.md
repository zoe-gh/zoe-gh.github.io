---
title: "Blog with Hexo and Github"
last_modified_at: 2022-06-09
categories: 
- Tools
tags: 
- Website
---

## Hexo setup

### Download Node.js and Git

Download and install [Node.js](https://nodejs.org/en/).
Download and install [Git](https://git-scm.com/downloads).
Open Powershell or CMD.
Check if downloads are successful:

    node -v
    npm -v
    git --version
    
 ## Download Hexo
 Download Hexo:

    npm install hexo-cli -g
Check if download is successful

    hexo -v
Optional: install code editor (VS Code, NotePad++, etc.)

### Set up Github

#### Set up Github repository

Create new repository for your blog.
Repository name: **[github_user_name].github.io**
Set repository as **Public**
Create brach **main** for publishing your blog.

#### Set up Github SSH

Generate SSH in Git Bash:

    $ ssh-keygen -t rsa -C "register.email@github.com"
    
Copy SSH from **id_rsa.pub** at **C:\Users\\[user_name]\\.ssh**
Github setting - SSH and GPG keys - SSH keys - Add new.
Input Title for SSH key, and paste SSH.
Check if successful:

    $ ssh -T register.email@github.com
   
### Set up Hexo

Create new project folder in Git Bash:

    $ hexo init <folder>  
	$ cd <folder>  
	$ npm install
Open **_config.yml** to change website settings: [How to set up configuration](https://hexo.io/docs/configuration)
Default theme is Landscape, see [Apply theme](http://localhost:4000) to change.
Apply changes to Hexo in Git Bash:

    $ hexo clean
    $ hexo g
Check your website demo on local server http://localhost:4000:

    $ hexo s
    
Ctrl + C to exit local server

### Generate New Post

    $ hexo new [post_name]

### Deploy to Github

Install deploy tool:

    $ npm install hexo-deployer-heroku --save

Open **_config.yml** to change delpoy settings: 

    deploy:

		type: git

		repo: https://github.com/[user_name]/[user_name].github.io.git

		branch: main

Deploy your website/changes to Github

    $ hexo d

View your staic website from: **https://[user_name].github.io/**

## Theme Hexo Blog with Butterfly

### Choose Hexo Theme

Default Theme is Landscape.
Choose your Hexo theme: [https://hexo.io/themes/](https://hexo.io/themes/)
Click image to view sample website, click theme name to get access to theme repository.
Here I recommend Butterfly:
- Powerful (toc, comment, wordcount, effect, etc.)
- Clear documentation
- Easy to customize

### Install Hexo Theme

Copy theme repository link.
Clone repository to local in Git Bash:

    $ git clone [repository_link] \themes\[theme_name]
Change theme configuration in _config.yml:

    theme: [theme_name]
Copy <code>/themes/[theme_name]/_config.yml</code> (theme specific config) to project folder, rename file to <code>_config.[theme_name].yml</code>

    $ npm install hexo-renderer-pug hexo-renderer-stylus --save


Customize your website using theme config file, see more in [Butterfly Tutorial](https://butterfly.js.org/posts/21cfbf15/).

### Customization in Butterfly

See [Butterfly Tutorial](https://butterfly.js.org/posts/21cfbf15/) for most customization.
1. Comment system
	- Recommend to use [Waline](https://waline.js.org/)

2. Theme color
	- Change in config <code>theme_color</code>
	- OR change in <code>/source/css/var.styl</code>

3. Background image
	- Set in config <code>background: url(img/bg_name.jpg)</code>
		- Able to use gif image
	- Advaned setting in <code>/source/css/_global/index.styl</code>
		- [See css format](https://www.w3schools.com/cssref/css3_pr_background.asp)

4. Card transparency
	- Change <code>$card-bg</code> in <code>/source/css/var.styl</code>
	- <code>$card-bg = rgba(r, g, b, a)</code>
		- a = opacity percentage

5. Footer
	- Add footer background image in config <code>footer_bg: url(/img/bg_name.jpg)</code>
	- Customize content in config <code>footer</code>
	- Change transparency and padding in <code>/source/css/_layout/footer.styl</code>

6. Pagination
	- Change `&.pagination-post` in <code>/source/css/_layout/pagination.styl</code>

