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
2. Follow the steps below:
    <details>
      <summary><b>Screenshots of the activation process:</b></summary>
    
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

![setup](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/desk1.png)

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
- Navigate to Appearance:
![Appearance](https://github.com/pcade/perfect-ubuntu-setup/blob/main/images/tweak.png)

- All user themes are stored in /usr/share/themes/, and icons are stored in /usr/share/icons/ and other corresponding directories. All installed themes and icons will be automatically displayed in GNOME Tweaks.