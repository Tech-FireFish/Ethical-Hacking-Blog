# Welcome to Day 1 of our Ethical Hacking Journal.

Every day, cybersecurity professionals defend networks, investigate attacks, and uncover security weaknesses before criminals can exploit them. Many of them begin with the same operating system you’ll install today: Kali Linux.

>Security is not about breaking things. It’s about understanding how they work.

A little bit of preparations if you did like to try to install Kali Linux on VirtualBox yourself:

- A Computer
- VirtualBox [Download here](https://www.virtualbox.org/wiki/Downloads)
- Kali Linux [Download here](https://www.kali.org/get-kali/#kali-platforms)

**Note:** If you want to get **started right away, download virtual machines** as your download option. Else if you would like to **customize your hardware settings, download image installer.**

Let’s dive in now. 😄

**Option 1 : Virtual Machines**

It’s pre-built. You can open it right away after unzipping it.

***To Install :***

Inside VirtualBox -> Click Open button or `Ctrl + A` to open the unzipped file -> Kali Linux is running(Done).

>The default username and password are `kali`.

**Option 2 : Image Installer**

It gives you more control over the hardware configuration. You have to configure hardware settings. Expect the installation to take about an hour.

***Requirements :***

| Level | Description | RAM | Storage |
| :---- | :---------: | :-: | ------: |
| Minimal | Basic Secure Shell (SSH) server without a desktop | 128 MB | 2 GB |
| Standard | Default Xfce4 desktop environment | 2 GB | 20 GB |
| Advanced | Better performance at resource-intensive tools | 8 GB | 20 GB |

***To Install:***

>A visual step-by-step guide is provided after the Credit section.

In VirtualBox -> Click on New button or `Ctrl + N` to create new virtual machine -> Fill out the highlighted fields:

- `VM Name` PC name.
- `VM Folder` place to store data.
- `ISO Image` system to install with the installer file.

Continue, `Right click` the newly created VM(virtual machine) -> select `settings` -> select `System` tab -> do the following the changes:

- Change the `Base memory` to a compatible number according to requirements.
- Enable the UEFI.

>UEFI is the modern firmware standard used by most computers. It supports newer hardware and features like Secure Boot.

Now, the basic hardware configuration is done. Let’s move on to actual installation by starting our Kali Linux VM.
The following are some terms you might found confusing during the installization.

- ***Domain name*** : It’s optional. Entering a domain name can better organize your computer on the network.

- ***LVM*** : Logical Volume Management(LVM) allows system administrators to combine multiple physical hard drives into a single flexible storage pool. (E.g. You can build your VM storage by taking 10 GB from D Drive and 10 GB from E Drive.)

- ***ESP*** is the mandatory partition on a GPT-formatted storage stores the files your computer needs to boot the operating system.

- ***EXT4*** (Fourth Extended Filesystem) is the standard and default filesystem used by most Linux distributions, including Ubuntu, Debian, and Fedora.

- “***swap***” in a disk partition acts as an overflow space for your physical RAM (Random Access Memory).(swap is slower than RAM)

- ***GNOME*** prioritizes a clean, distraction-free, and streamlined workflow, heavily relying on keyboard and touchpad gestures.

- ***KDE Plasma*** favors deep customization, offering a traditional, Windows-like desktop and vast control over every visual detail.

Congratulations. You made it all the way here. 😄

# Credits
[GO BACK TO REFERENCE](#reference)

- Tech-FireFish, Contributor, [Profile_URL](https://github.com/Tech-FireFish)
- IBM Ethical Hacking with Open Source Tools Professional Certificate instructed by IBM Skills Network Team, Dee Dee Collette, Christo Oehley on Coursera platform, 2024, [URL](https://www.coursera.org/professional-certificates/ibm-ethical-hacking-with-open-source-tools).

![images/virtual_machine_setup_step1](./images/virtual_machine_setup_1.png)

![images/virtual_machine_setup_step2](./images/virtual_machine_setup_2.png)

![images/virtual_machine_setup_step3](./images/virtual_machine_setup_3.png)

![images/virtual_machine_setup_step4](./images/virtual_machine_setup_4.png)

![images/virtual_machine_setup_step5](./images/virtual_machine_setup_5.png)

![images/virtual_machine_setup_step6](./images/virtual_machine_setup_6.png)

![images/virtual_machine_setup_step7](./images/virtual_machine_setup_7.png)

![images/virtual_machine_setup_step8](./images/virtual_machine_setup_8.png)

![images/virtual_machine_setup_step9](./images/virtual_machine_setup_9.png)

![images/virtual_machine_setup_step10](./images/virtual_machine_setup_10.png)

![images/virtual_machine_setup_step11](./images/virtual_machine_setup_11.png)

![images/virtual_machine_setup_step12](./images/virtual_machine_setup_12.png)

![images/virtual_machine_setup_step13](./images/virtual_machine_setup_13.png)

![images/virtual_machine_setup_step14](./images/virtual_machine_setup_14.png)

![images/virtual_machine_setup_step15](./images/virtual_machine_setup_15.png)

![images/virtual_machine_setup_step16](./images/virtual_machine_setup_16.png)

![images/virtual_machine_setup_step17](./images/virtual_machine_setup_17.png)

![images/virtual_machine_setup_step18](./images/virtual_machine_setup_18.png)

![images/virtual_machine_setup_step19](./images/virtual_machine_setup_19.png)

![images/virtual_machine_setup_step20](./images/virtual_machine_setup_20.png)

![images/virtual_machine_setup_step21](./images/virtual_machine_setup_21.png)

**ALL DONE**
