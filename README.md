![Gazee](/public/images/logos/red/logo-red-yellow.png)

[![Build Status](https://travis-ci.org/hubbcaps/gazee.svg?branch=master)](https://travis-ci.org/hubbcaps/gazee)

# This Project is currently no longer in development. Life took over and I didn't have the motivation to continue.
# If you'd like to take over development, feel free to fork and run with it.
# The main thing it needs currently is an ORM to replace all the hardcoded DB interactions.

# I highly suggest taking a look at [Codex](https://github.com/ajslater/codex/tree/release/codex), this application is in current development and does everything I wanted Gazee to be and more.

Gazee is a comic viewer for the web browser.

Read and reach your favorite digital comics from almost any web connected device.

Works great with [Mylar](https://github.com/evilhero/mylar) comic book management, but not needed.

Check out [the Wiki](https://github.com/hubbcaps/gazee/wiki) for detailed instructions on setup if you need them.

Questions can also be asked in the #gazee channel on Freenode

## Features

Recent Comics
![screen01](https://i.imgur.com/WiqlTSV.png)

Exposes your sorting structure in a library view
![screen02](https://i.imgur.com/NNn17XR.png)
Download your issue if you have a preferred reader outside of Gazee and read a summary of the issue in line if available with your archive
![screen03](https://i.imgur.com/EbnpMZS.png)

Make Gazee yours and change up the color scheme
![screen04](https://i.imgur.com/OyFsZqE.png)
![screen05](https://i.imgur.com/VkhRvid.png)

Now with logo changer
![screen06](http://i.imgur.com/iIoyalA.gif)

Settings overlay to make the comic feel how you want it.
![screen06](https://i.imgur.com/nE3k7j8.png)

HTTPS Support

Bookmarks remember where you left off as you read.

Multiple Users and Admins

Much more to come!

## Requirements
* Python 3.4+
* CherryPy
* Mako
* xmltodict
* Pillow
* rarfile
* GitPython

Requirements can be installed easily in the setup section below.

#### Unrar Downloads

Unrar needs to be installed and visible in the path of the user Gazee is running under to be able to properly extract all CBRs.

Double check this on Windows, different systems have different requirements for making sure you have unrar visbile in your users path.

[Unrar for Windows](http://www.rarlab.com/rar_add.htm), windows also needs command line accessible Git installed, gone over in the [install guide on the wiki](https://github.com/hubbcaps/gazee/wiki/Windows-Install-Guide)

[Centos](https://www.rpmfind.net/linux/rpm2html/search.php?query=unrar) needs Unrar from RPMFusion, not Offical/EPEL unar application. unar is out of date and will fail with certain types of cbrs and other rar archives.

[Debian](https://packages.debian.org/jessie/unrar)

## Setup

**Step 1: Clone the repository and install python dependencies**

    cd <directory you want to install to>
    git clone https://github.com/hubbcaps/gazee.git
    cd gazee
    sudo pip install -r requirements.txt
    python Gazee.py
    
**Note**
If you see an error similar to the following

    $ python Gazee.py
    File "Gazee.py", line 194
    cherrypy.engine.timeout_monitor.on: False
    ^
    SyntaxError: invalid syntax

This likely means your systems default version of python is 2.x. Verify you have python 3.4+ installed and call it explicitly with python3 or python3.x

    python3 Gazee.py

**Step 2: Logon to Gazee's Web UI**)

  Go to **http://your-ip:4242**
  
  Default username and password for the web interface:
  
  * **Username:** `admin`
  * **Password:** `gazee`
  
  Proceed to the settings page and change your admin pass, and enter the path to your comic library   and optionally your Mylar DB for better comic info extraction.

### Daemonize (Linux only)

You can easily run the program in Daemon mode by using the -d flag

    python Gazee.py -d

## Docker Container

Alternatively, instead of doing a local install, you can install the docker container.

The docket container can be pulled from [here](https://github.com/hubbcaps/docker-gazee) or from [dockerhub](https://hub.docker.com/r/hubcapps/gazee/).

### QOL Features on the Roadmap

These are features that will make Gazee better and more up to par in what should be expected of a modern comic reader, but aren't needed for actual usability.

- [ ] Random First Issue of a series in library.
- [ ] OPDS Support.
- [ ] User set image sizes.
- [ ] Notifications on new comics
- [ ] Reports on various stats of your library; number of bad archives, comics without metadata, etc etc
