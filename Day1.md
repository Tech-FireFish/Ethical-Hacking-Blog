# Introduction
This note will contains practical skills for ethical hacking.

# Reference
- [Overview of Kali Linux](#overview-of-kali-linux)
- [Credits](#credits)


# Overview of Kali Linux
[GO BACK TO REFERENCE](#reference)

### Setting up VirtualBox
- Download VirtualBox [here](https://www.virtualbox.org/wiki/Downloads).
### Setting up Kali Linux
- Download Kali Linux [here](https://www.kali.org/get-kali/#kali-platforms)

*Options Explained:*
- ***Virtual Machines***
> It's pre-built. You can open it right away after unzipe it.

**Install:**

*In VirtualBox -> Click Open button or `Ctrl + A` to open the unzipped file -> Kali Linux is running(Done).*

> The default user and passwd is `kali`.

- ***Installer Images***
> It provides complete control over the hardware access. You have to configure hardware settings.

*Requirements*

| Level | Description | RAM | Storage |
| :---- | :---------: | :-: | ------: |
| Minimal | Basic Secure Shell (SSH) server without a desktop | 128 MB | 2 GB |
| Standard | Default Xfce4 desktop environment | 2 GB | 20 GB |
| Advanced | Better performance at resource-intensive tools | 8 GB | 20 GB |

**Install:**

*In VirtualBox -> Click on New button or `Ctrl + N` to create new virtual machine -> Fill out the highlighted portions:*
- `VM Name` PC name, 
- `VM Folder` place to store data, 
- `ISO Image` system to install with the installer file.

![virtual_machine_setup_step1](./images/virtual_machine_setup_1.png)

*Continue, `Right click` the created VM(virtual machine) -> slect `settings` -> select `System` tab -> do the following the changes:*
- change the `Base memory` to a compatibale number according to requirements, 
- enable the UEFI
> *UEFI enables* Advanced security(*Secure Boot*), *support lager disks* size than 2 TB, and better performance(*parallel computing*).

![images/virtual_machine_setup_step2](./images/virtual_machine_setup_2.png)

*Now, the basic hardware configuration is done. Let's move on to actual installation by starting our Kali Linux VM. Here is the Graphical User Interface.* (Command-line Interface is in processing)

*Click on the first two options to get start. (option 2 Install is the same thing but a more classic interface)*

![images/virtual_machine_setup_step3](./images/virtual_machine_setup_3.png)

*Next, select a language you perform.*

![images/virtual_machine_setup_step4](./images/virtual_machine_setup_4.png)

*Select a lcation you perform to use for time zone.*

![images/virtual_machine_setup_step5](./images/virtual_machine_setup_5.png)

*Select a keyboard setting you perform.*

![images/virtual_machine_setup_step6](./images/virtual_machine_setup_6.png)

*Name your PC(this name will show on the network)*

![images/virtual_machine_setup_step7](./images/virtual_machine_setup_7.png)

*Enter your domain name you perform(Optional)*

![images/virtual_machine_setup_step8](./images/virtual_machine_setup_8.png)

*Enter a fullname you perform.(used to identify accounts)*

![images/virtual_machine_setup_step9](./images/virtual_machine_setup_9.png)

*Enter a username you perform.(used in login page)*

![images/virtual_machine_setup_step10](./images/virtual_machine_setup_10.png)

*Enter a password you perform.(used in login page)*

![images/virtual_machine_setup_step11](./images/virtual_machine_setup_11.png)

*Select a time zone you perform.*

![images/virtual_machine_setup_step12](./images/virtual_machine_setup_12.png)

*Select a parition method you perform.*
> LVM or Logical Volume Management allows system administrators to combine multiple physical hard drives into a single flexible storage pool. Ex: You can build your VM storage by taking 10 GB from D Drive and 10 GB from E Drive.

![images/virtual_machine_setup_step13](./images/virtual_machine_setup_13.png)

*Confirm the disk to use*

![images/virtual_machine_setup_step14](./images/virtual_machine_setup_14.png)

*Select a file structure you perform.*

![images/virtual_machine_setup_step15](./images/virtual_machine_setup_15.png)

*Confirm parition settings you perform.*
> ESP is the mandatory partition on a GPT-formatted storage drive that acts as the bridge between your computer's hardware and its operating systems.

> EXT4 (Fourth Extended Filesystem) is the standard and default journaling file system used by most Linux distributions, including Ubuntu, Debian, and Fedora.

> swap in a disk partition acts as an overflow space for your physical RAM (Random Access Memory).

![images/virtual_machine_setup_step16](./images/virtual_machine_setup_16.png)

*Select `Yes` to confirm the parition*

![images/virtual_machine_setup_step17](./images/virtual_machine_setup_17.png)

*Processing...*

![images/virtual_machine_setup_step18](./images/virtual_machine_setup_18.png)

*Select a visual interface you perform*
>GNOME prioritizes a clean, distraction-free, and streamlined workflow, heavily relying on keyboard and touchpad gestures. 

>KDE Plasma favors deep customization, offering a traditional, Windows-like desktop and vast control over every visual detail.

![images/virtual_machine_setup_step19](./images/virtual_machine_setup_19.png)

*Processing...*

![images/virtual_machine_setup_step20](./images/virtual_machine_setup_20.png)

*Congraduation.*

![images/virtual_machine_setup_step21](./images/virtual_machine_setup_21.png)

# Credits
[GO BACK TO REFERENCE](#reference)

- Tech-FireFish, Contributor, [Profile_URL](https://github.com/Tech-FireFish)
- IBM Ethical Hacking with Open Source Tools Professional Certificate instructed by IBM Skills Network Team, Dee Dee Collette, Christo Oehley on Coursera platform, 2024, [URL](https://www.coursera.org/professional-certificates/ibm-ethical-hacking-with-open-source-tools).
