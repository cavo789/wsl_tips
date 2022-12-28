# WSL / WSLg - How to

![Banner](./banner.svg)

## Install from fresh

* Start a PowerShell console with admin rights and run `wsl --set-default-version 2` to, just, make sure we'll use WSL2 as default
* Click on [https://aka.ms/wslstorepage](https://aka.ms/wslstorepage) to start the *Microsoft Store* application and install *Windows Subsystem for Linux*. *(Note: It is highly recommended to use the Microsoft Store version of WSL, which supports both Windows 10 and Windows 11, and contains the most up to date version of WSL and WSLg.)*
* Back to the PowerShell console, run `wsl --install -d Ubuntu` for installing the latest version of Ubuntu *(Note: you can choose another distribution like Debian f.i.)*.
	* A new, Linux, console, will be started and you'll need to provide the name and password for your admin account. By preference, don't keep `root` but change it to, f.i., your firstname
* Reboot your computer.
* Start your Ubuntu console (one way is to click on the Windows start button and run `Ubuntu`)

## Move to another location

> [https://dev.to/mefaba/installing-wsl-on-another-drive-in-windows-5c4a](https://dev.to/mefaba/installing-wsl-on-another-drive-in-windows-5c4a)

This step is optional.

By default, the Linux distribution is installed on your `C:` drive. If you want to install it on f.i. `D:` please follow the next steps:

* Run `wsl --list --verbose` from a PowerShell console; you'll get the name of your distribution (`Ubuntu` in my case),
* From a PowerShell Admin console, run `wsl --terminate Ubuntu`,
* On your second drive, create a temporary folder like `mk wsl`,
* Run `wsl --export Ubuntu "d:\wsl\ubuntu.tar"`,
* When finished, run `wsl --unregister Ubuntu` and, finally,
* Run `wsl --import Ubuntu "d:\wsl\ubuntu" "d:\wsl\ubuntu.tar"`

You'll need to do this for every distribution you've installed. If you've Docker, you can do the same i.e. move the Docker partition to your second disk.

## Play with the console

* Just click on the Windows Start button and run `ubuntu` to start a console
* Run `whoami` on the console to see which user has been used by default.
* If you see `root` and this is not the one you wish as the default one (let's say you wish to connect as `christophe`), just start a PowerShell console and run `ubuntu config --default-user YOUR_FIRSTNAME`.
* You can type any Linux command here like `ls`, `pwd`, ...

## Play with graphical interfaces

> [https://github.com/microsoft/wslg](https://github.com/microsoft/wslg)
>
> [https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps](https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps)

* Important, make sure everything is up-to-date by running `sudo apt update`.
* Install tools like `gedit` or `gimp`: `sudo apt install gedit -y` or `sudo apt install gimp -y`. 
* From the Ubuntu console, just execute the installed application by running `gedit` or `gimp`.

## Now time to install ZSH

ZSH is an extended version of the Bourne Shell (sh), with plenty of new features, and support for plugins and themes. Since it's based on the same shell as Bash, ZSH has many of the same features, and switching over is a breeze.

Jump to [https://github.com/cavo789/oh-my-zsh-tips](https://github.com/cavo789/oh-my-zsh-tips) for more information and how to install guide.
