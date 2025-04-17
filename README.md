# My ideal Ubuntu: customizing the system to suit my needs.

Customizing Ubuntu for Personal Tasks — Crafting Your Own Comfort Zone
In this article, I’ll share my experience tailoring Ubuntu to fit my workflow. These tweaks might save you time and spare you from unnecessary trial and error. All examples were tested on Ubuntu 22.04 LTS, though many ideas apply to other versions too.

## Ubuntu Pro — Why Not?

Many colleagues were surprised to learn about the free Ubuntu Pro subscription. Here’s why it’s worth considering:

- Extended support: LTS versions receive updates for 10 years instead of 5.
- Enhanced security: Expanded security patches for repositories.
- Critical component protection: Mitigation for vulnerabilities in core packages.

#### How to Activate Ubuntu Pro

1. Visit the [subscription page](https://ubuntu.com/pro).
2. <details>
      <summary><b>Follow the steps below:</b></summary>
    
      ![Click "Get Ubuntu Pro now"](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/reg1.png)
      
      Click "Get Ubuntu Pro now".

      ![Select "Myself".](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/reg2.png)
      
      Select "Myself".

      ![Register an account if you don’t have one.](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/reg3.png)
      
      Register an account if you don’t have one.

      ![Confirm with "Yes, log me in".](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/reg4.png)
      
      Confirm with "Yes, log me in".

      ![Copy the command under "Command to attach machine:".](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/reg5.png)
      
      Copy the command under "Command to attach machine:".

    </details>

3. Run the copied command in your terminal:
    ```bash
    sudo pro attach <your_token>  
    ```
**<span style="background-color:#F5F5F5"><span style="color:black">While some may view these security perks as abstract, why not take advantage of free Pro features?</span></span>**

## Drivers — Ubuntu Handles It All
- One of Ubuntu’s strengths is automatic driver management. After installation, run:
    ```bash
    sudo ubuntu-drivers autoinstall
    ```
- Ubuntu will then notify you of driver updates and install them automatically at startup.
<details>
  <summary><b>Example notification:</b></summary>

![Example notification"](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/driver.png)
</details>

## GNOME Extensions — Bring Your Desktop to Life

Out of the box, GNOME feels bland. But with [extensions.gnome.org](extensions.gnome.org), it becomes a canvas for creativity. Here’s my setup:
<p align="center">
  <img src="https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/desk1.png" alt="setup">
</p>

#### Required Packages

- Install these to manage GNOME extensions:
  ```bash
  sudo apt install chrome-gnome-shell gnome-tweaks
  ```
- Visit [extensions.gnome.org](extensions.gnome.org) in your browser.
- Enable the browser extension for GNOME integration.
<details>
  <summary><b>Extensions:</b></summary>

![Extensions](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/ext1.png)
</details>

><span style="background-color:yellow"><span style="color:green">Tip </span></span><span style="color:black">: Avoid overloading your system with extensions—they impact performance, and half may go unused.</span>

## Desktop Customization

- Open GNOME Tweaks.
- <details>
    <summary><b>Navigate to Appearance:</b></summary>

    ![Appearance](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/tweak.png)
  </details>

- All user themes are stored in /usr/share/themes/, and icons are stored in /usr/share/icons/ and other corresponding directories. All installed themes and icons will be automatically displayed in GNOME Tweaks.

## Zsh + Aliases + SSH Config — Supercharge Your Terminal

#### Install Zsh and Oh My Zsh

```bash
sudo apt install zsh  
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
#### Set Zsh as default
```bash
chsh -s $(which zsh)
```
#### Aliases for Efficiency
- An alias is a convenient shortcut for frequently used commands that helps speed up work in the terminal. To set up an alias in Zsh, open the configuration file ~/.zshrc and ~/.bashrc in Bash, respectively. Below is my example of alias configuration that may be useful:
- <details>
    <summary><b>Alias example:</b></summary>

    ```
    # Shortened command for ls -la
    alias ll='ls -la'
    # Shortened command to clear the terminal
    alias c='clear'
    # Shortened command for apt with sudo
    alias apt='sudo apt-fast'
    # Shortened command for nano
    alias nn='nano'
    # Shortened command to go up one directory
    alias ..='cd ..'
    # Shortened command to exit the terminal
    alias q='exit'
    # Shortened command for updating and upgrading the system
    alias uu='sudo apt-fast update && sudo apt-fast upgrade'
    # Shortened command to view command history
    alias h='history'
    # Shortened command to search for a file
    alias ff='find / -type f -name'
    # Shortened command to search for a directory
    alias fd='find / -type d -name'
    # Shortened command to display the current time
    alias date='date +%H:%M:%S'
    # Time and date format in history
    export HISTTIMEFORMAT='%F %T '
    # Shortened commands for rebooting, shutting down, and halting the system
    alias reboot='sudo /sbin/reboot'
    alias poweroff='sudo /sbin/poweroff'
    alias halt='sudo /sbin/halt'
    alias shutdown='sudo /sbin/shutdown'
    # Confirmation when overwriting files
    alias mv='mv -i'
    alias cp='cp -i'
    alias ln='ln -i'
    # Protection against deleting the root directory and confirmation when deleting more than 3 files
    alias rm='rm -I --preserve-root'
    # Limit on the number of packets sent with ping
    alias ping='ping -c 5'
    # Fast ping without waiting for an interval
    alias fastping='ping -c 100 -s 0.2'
    ```
  </details>

## Recommended Packages
#### Apt-fast — Faster Downloads
- Replace apt with a multithreaded alternative:
  ```bash
  sudo add-apt-repository ppa:apt-fast/stable
  sudo apt update && sudo apt install apt-fast
  ```
#### Terminator — Advanced Terminal
<p align="center">
  <img src="https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/term.png" alt="Terminator">
</p>
- Flexible screen splitting - You can split the terminal window into multiple panes and work with several sessions simultaneously.
- Advanced interface settings - A variety of options for customizing the appearance and behavior of the terminal.
  ```bash
  sudo apt install terminator
  ```
- Below is the method for installing Terminator as the primary terminal:
  ```bash
  sudo update-alternatives --config x-terminal-emulator
  sudo apt-get remove gnome-terminal
  sudo ln -s /usr/bin/terminator /usr/bin/gnome-terminal
  ```