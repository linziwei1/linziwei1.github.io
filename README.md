##Building##
> In the past two days, I rebuilt the blog on Github Pages and switched to jekyll, which is similar to the previous hexo, mainly talking about the environment.

> There are also BUGs who want to cry =。=

> Anyway, let's get to the point.

##System Environment Building ###
First install jekyll, which is the static web tool recommended by GitHub. It's similar to WordPress, but it's just a tool for generating static web pages that doesn't require database support. It can also be used with third-party services such as Disqus.
### First install ruby ​​###
> [ install git ](http://git-scm.com/download/)

> [ Install ruby ​​and devkit tools ](https://rubyinstaller.org/downloads/)  

Check to add to the PATH during installation to add environment variables.
> There is a place for wawawa. The installation path must not be in the secondary directory. It can only be installed directly under the directory of the drive letter. Otherwise, there will be a bunch of problems that Baidu and Google can't solve. Don't ask me how to know=，=

![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/1.jpg)
After the installation is complete, continue to install msys2, directly select finish to enter the installation interface.
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/2.jpg)
Then select the third item (input 3) and wait for the installation prompt to close and then close.
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/3.jpg)

### Installing RubyGems ###
Ruby is a language that is the execution environment for some package code. Gem is a program that manages these ruby-based programs.

> [ Install RubyGems ](https://rubygems.org/pages/download)
>
> It is convenient to download the ZIP format in Windows. After downloading, extract it to any path.

Perform the following instructions to install
```bash
$ cd {unzip-path} // unzip-path indicates the path to decompress
$ ruby ​​setup.rb
```

### Install jekyll ###
Input instruction installation in cmd
```bash
$ gem install jekyll
$ gem install "jekyll-paginate"
```

### Verifying the installation is complete ###
Enter in cmd:
```bash
$ jekyll -v
```
Successfully outputting the version number indicates that the installation was successful.


## Open local live preview ##
Switch to the directory where the repository is located and type in cmd:
```bash
$ jekyll serve
```

![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/4.jpg)
You can see the effect by visiting http://127.0.0.1:4000/.

> Sometimes you will encounter the jekyll serve startup error as follows. This is because jekyll uses 4000 ports by default, and 4000 is the default port for FoxitProtect (a service for Foxit Reader). The easiest way is to specify a port, for example:

```bash
Incremental build: disabled. Enable with --incremental
      Generating...
Jekyll 3.7.3 | Error: Permission denied @ rb_sysopen - C:/Users/username/NTUSER.DAT
```

```bash
$ jekyll serve -P 5555
```

Then write the article to write an article, the custom function code is customized. . . . . .

## push to GitHub ##
The local blog is done, and the next step is on the line. It is basically consistent with the general project process.
First create a new project, then clone it and put all the local files into it first. (Not cloned or cloned from another code will not work)

### Local Add SSH ###
#### 1. First, you need to check if your computer already has SSH key ####
Run the git Bash client and enter the following code:
```bash
$ cd ~/.ssh
$ ls
```
These two commands are to check if the id_rsa.pub or id_dsa.pub file already exists. If the file already exists, you can skip step 2 and go directly to step 3.

#### 2, create a SSH key ####
```bash
$ ssh-keygen -t rsa -C "your_email@example.com"
```
Code parameter meaning:
-t Specifies the key type. The default is rsa and can be omitted.
-C Set the comment text, such as the mailbox.
-f Specifies the key file storage file name.

The above code omits the -f parameter, so running the above command will let you enter a filename to save the SSH key code you just generated, such as:
```bash
Generating public/private rsa key pair.
# Enter file in which to save the key (/c/Users/you/.ssh/id_rsa): [Press enter]
```
Of course, you can also use the default file name (recommended) without entering the file name, then the two key files id_rsa and id_rsa.pub will be generated.

Then you will be prompted to enter the password twice (this password is the password you want to enter when you push the file, not the password of the github administrator).

Of course, you can also press Enter without entering the password (two carriage returns, one input, one confirmation). Then push does not need to enter the password, directly submitted to github.

#### 3. Add your SSH key to github. ####
a. Find the corresponding id_rsa.pub file according to the generated file address, and open the key with the tool such as notepad++.

b. Log in to your github account, enter it from the Account Settings in the upper right corner, and then click SSH key in the menu bar to enter the page to add the SSH key.

c. Click the Add SSH key button to add an SSH key. Paste your copied SSH key code into the input box corresponding to key. Remember to leave no spaces or carriage returns before and after the SSH key code. Of course, you can also enter an alias for the SSH key displayed on github in the input box corresponding to Title above. By default, your mail name will be used.
[![iYuNxe.png](https://s1.ax1x.com/2018/10/09/iYuNxe.png)](https://imgchr.com/i/iYuNxe)

#### 4, test the SSH key ####
Enter the following code in git Bash
```bash
$ ssh -T git@github.com
```
When you enter the above code, there will be a warning code, such as:
```bash
The authenticity of host 'github.com (207.97.227.239)' can't be established.
# RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
# Are you sure you want to continue connecting (yes/no)?
```
This is normal, you can enter yes to enter. If you set a password when you create the SSH key, you will be prompted to enter your password, such as:
```bash
Enter passphrase for key '/c/Users/Administrator/.ssh/id_rsa':
```
Of course, if you enter the wrong password, you will be asked to enter it. Of course, if you call back twice, you don't have to worry about it here.

Note: If you enter password with a wrong char, it will be incorrect. You can't correct it by using the delete key.

After the password is correct, you will see the following paragraph, such as:
```bash
Hi username! You've recently authenticated, but GitHub does not
# provide shell access.
```
If the username is correct, you have successfully set up the SSH key. If you see "access denied" and you are denied access, then you need to use https to access instead of SSH.

### Upload Start ###
---
> Right-click git bash in the blog directory and enter the following code:

```bash
Git config --global user.email "your GitHub mailbox"
Git config --global user.name "your GitHub username"
```
The following can be officially released!
```bash
Git add .
Git commit -m "submit information"
Git push
```
If you have not reported an error, you can use "your username.github.io" as the address to browse.

## Want a better remembered domain name? ##
If you think that the above domain name is not very easy to remember, you can go to Tencent Cloud or Wanwang to register a new domain name, and then add the resolution to the github.io space.
PS: One of the benefits of GitHub Pages is that it is exempt from filing. Of course, the downside is that space and speed are sacrificed, but it is enough for individual users.

## About picture storage ##
Due to server speed and space limitations, our best practice is to host the picture on the network map bed, you can recommend [七牛云](https://www.qiniu.com/) (but this product needs you to upload handheld ID card photos can give you 10G, so I gave up), [路过图床](https://imgchr.com/) (free registration, I am using it now).

Update: The best way is actually Sina Weibo map bed, this can search for Chrome plug-ins by yourself, very easy to use, Sina Weibo's server is absolutely fast and stable.

What's the fucking update plus: Free lunch is not fragrant, Sina restricts the outer chain, killing people! ! ! Spend money to buy an OSS in Aliyun and then pass it on yourself, the most rest assured!


## Jekyll-Search ##
需要用到一个插件[simple-jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search)

### Create search.json ###
```bash
---
layout: null
---
[
  {% for post in site.posts %}
    {
      "title"    : "{{ post.title | escape }}",
      "category" : "{{ post.category }}",
      "tags"     : "{{ post.tags | join: ', ' }}",
      "url"      : "{{ site.baseurl }}{{ post.url }}",
      "date"     : "{{ post.date }}"
    } {% unless forloop.last %},{% endunless %}
  {% endfor %}
]
```
### Copy JS ###
Copy simple-jekyll-search.min.js to the root/js  of site from the project.

### Update nav.html ###
As for this theme,we need to update***_includes/nav.html***.
Code:Insert to  the html.

```bash
<!-- HTML elements for search-->
<div id="search-container" style="float:right;position: fixed;right:0px; bottom:10px; z-index:999999;background:#eeeeee;padding:10px 10px 0px 10px;">
  <input type="text" id="search-input" placeholder="search..." style="border:2px solid;border-radius:25px;padding-left:10px !important;" >
  <ul id="results-container" style="max-width:300px;"></ul>
</div>

<!-- script pointing to jekyll-search.js-->
<script src="{{ site.baseurl }}/js/simple-jekyll-search.min.js"></script>

 <script>
      window.simpleJekyllSearch = new SimpleJekyllSearch({
        searchInput: document.getElementById('search-input'),
        resultsContainer: document.getElementById('results-container'),
        json: '{{ site.baseurl }}/search.json',
        searchResultTemplate: '<li><a href="{url}" title="{desc}">{title}</a></li>',
        noResultsText: 'No results found',
        limit: 5,
        fuzzy: false,
        exclude: ['Welcome']
      })
    </script>

```
