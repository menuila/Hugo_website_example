# Introduction

The main purpose of this share is to show you how to build your own website using a site generator in order to facilitate and improve the creation of one of them. Please follow the instructions to start creating your own one.

# Hugo configuration in Ubuntu Server

**Install Hugo**

	apt-get install hugo

**Create new site**

	hugo new site Hugo_name_site
	
**Download theme**

| Command  | Description |
| :------------- | :------------- |
| cd Hugo_name_site/ | Enter to the new site  |
| git init  | Initizalize Git  |
| cd themes/  | Go to themes |
| git clone https://github.com/escalate/hugo-split-theme.git  | Clone theme template from https://themes.gohugo.io/   |
| cd hugo-split-theme  | Enter to the theme  |
| ls -l  | List the files |
| cd Hugo_name_site/  | Go back to the main folder  |
| cp theme/hugo-split-theme/exampleSite/* -rf ~/Hugo_name_site/  | Copy all example folder to the main site folder  |
| hugo server -D --bind 192.168.1.37 --baseURL 192.168.1.37  | Test the server specifing the IP address |

**Edit the site**

Check the theme git description, make sure to edit `https://example.com` with your own domain or IP Address in the `config.toml` file located in the site `(Hugo_name_site/ folder)`

**Publish the website**

| Command  | Description |
| :------------- | :------------- |
| hugo -D | It will create a public/ folder with all website configuration  |



# GitHub Configuration

**Initialize github in the folder you need to upload**

	git init

**Check status and see the branch**

	git status

**Add files**

| Command  | Description |
| :------------- | :------------- |
| git add . | Add all files  |
| git add public/  | Add a specific folder |
	 	

**Add the commit**

	git commit -m "commit comments"

**Define the repo URL where are you going to push the files**

	git remote add origin https://github.com/applaudo-gcp-tp/mnuila_W1_challenge_hugo.git

**Push the files (master is the branch, check "git status")**

	git push -u -f origin master



# Webserver Apache Configuration

**Update apt**

	sudo apt update

**Upgrade apt**

	sudo apt upgrade
	
**Install apache**

	sudo apt install apache2 -y

**Move to default main apache directory and copy Hugo static website**

| Command  | Description |
| :------------- | :------------- |
| cd /var/www/html/ | Go to main HTML directory  |
| git init | Init GitHub |
| git clone https://github.com/applaudo-gcp-tp/mnuila_W1_challenge_hugo.git --branch master | Clone repository |
| service apache2 restart | Restart apache  |
		
**Go the website**

http://192.168.1.27/mnuila_W1_challenge_hugo



# Architecture diagram

![mnuila_W1_diagram_v2](https://user-images.githubusercontent.com/67451983/193164266-0d581343-dbbf-4cb5-8999-5d337e4cfeda.png)
[Architecture Diagram -  Challenge 1.pdf](https://github.com/applaudo-gcp-tp/mnuila_W1_challenge_hugo/files/9679766/Architecture.Diagram.-.Challenge.1.pdf)

The diagram below explains the architecture for the web site designed using a WebSite generator, which is represented as follows:

The `gray box` represents the end user who is attempting to access the website via HTTP.

The `blue box` represents the webserver as well, which can be physical or virtual and host the website. This box is `administrated by the developers` who are responsible for updating the website by `"pulling"` the data from a private repository on GitHub.

The `green box` represents the website generator server, which facilitates the design for the website, allowing us to create different websites using templates or themes provided by Hugo. It can be installed on a physical or virtual server. This box is `administrated by the developers` who are responsible for creating new content by `"pushing"` the data to a private repository on GitHub.

The `white box` represents what the `developers are in charge of.`

The `orange box` represents what `DevOps are responsible for.` In this case, providing the necessary architecture in order to allow correct communication and deployment for the website.

This scenario is thought to show the basic methodology `"github action"` for software deployment.



# Website example

![Website](https://user-images.githubusercontent.com/67451983/193303414-b9ce9e87-7726-486a-9745-bea4fcdc0f56.png)
