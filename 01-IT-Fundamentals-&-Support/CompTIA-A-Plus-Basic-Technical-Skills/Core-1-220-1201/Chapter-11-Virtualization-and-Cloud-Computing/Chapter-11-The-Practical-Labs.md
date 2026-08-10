### 🛠️ Lab 1: Enabling a Type 1 Hypervisor — Turning On Hyper-V in Windows 11

**Objective:** Verify a physical machine meets Type 1 hypervisor requirements, enable Microsoft Hyper-V through Windows Features, and confirm it's running by opening Hyper-V Manager — reinforcing this chapter's distinction between a bare-metal hypervisor and the physical hardware it manages directly.

**Environment/Tools Needed:** A PC running Windows 11 Pro or Enterprise (Hyper-V is not available on Windows 11 Home) with a 64-bit processor supporting Second Level Address Translation (SLAT) and CPU virtualization extensions (Intel VT-x/VT-c or AMD-V), at least 4 GB of RAM, and administrator rights.

**Step-by-Step Instructions:**

1. Confirm your edition of Windows supports Hyper-V: open Settings → System → About and check the Windows specifications for "Pro" or "Enterprise." If it says "Home," Hyper-V cannot be enabled on this machine — read through the remaining steps for reference instead of performing them.
2. Confirm virtualization is enabled in the BIOS/UEFI. Restart the PC, enter the BIOS/UEFI setup (commonly `Del`, `F2`, or `F10` at boot — check your manufacturer's documentation), and locate a setting called Virtualization Technology, Intel VT-x, AMD-V, or SVM Mode. Ensure it's enabled, then save and exit.
3. Back in Windows, open the Start menu and type `windows features`. Select **Turn Windows Features On Or Off** when it appears.
4. In the Windows Features list, scroll down and locate the **Hyper-V** entry. Click the checkbox to select it (this automatically selects its sub-components, Hyper-V Management Tools and Hyper-V Platform) and click **OK**.
5. Wait for Windows to apply the changes. When prompted, click **Restart Now** to complete the installation.
6. After the machine restarts and you're back at the desktop, open the Start menu, type `Hyper-V`, and press Enter to launch **Hyper-V Manager**.
7. In Hyper-V Manager, click your PC's name in the left-hand navigation pane. Confirm the main window shows a Virtual Machines pane (currently empty) and an Actions pane on the right listing options like **New → Virtual Machine**.
8. Write two to three sentences explaining, based on this chapter, why Hyper-V is classified as a Type 1 (bare-metal) hypervisor even though you just installed it through a normal Windows Features menu rather than as separate standalone software.

**Expected Result:** Hyper-V successfully enabled without errors, a completed restart, and Hyper-V Manager opening to show your machine ready to host new virtual machines — plus a short written explanation connecting the installation process back to the Type 1 bare-metal classification.

---

### 🛠️ Lab 2: Building a Type 2 Cloning Chamber — Installing VirtualBox and a Linux Guest OS

**Objective:** Install a Type 2 (hosted) hypervisor on top of an existing host OS, create a new virtual machine, and boot a real guest OS inside it — directly reinforcing this chapter's Type 2 hypervisor definition and the RAM/storage requirements a guest OS adds on top of the host.

**Environment/Tools Needed:** A Windows, macOS, or Linux PC with at least 8 GB of RAM (4 GB minimum for the host OS plus roughly 2–4 GB for the guest) and at least 15 GB of free disk space, an internet connection, `Oracle VirtualBox` (free download from `virtualbox.org`), and a lightweight Linux ISO such as `Lubuntu` (free download from `lubuntu.me/downloads`) or any other distribution of your choice.

**Step-by-Step Instructions:**

1. Download VirtualBox for your host OS from `virtualbox.org/wiki/Downloads` and download a Linux ISO (Lubuntu or similar) from its official site. Save both to a location you'll easily find, such as the desktop.
2. Run the VirtualBox installer, accepting the default options through the setup wizard. If prompted about a temporary network interface interruption, accept it — your network connection will restore automatically once installation finishes. Click **Install**, approve any OS security prompts, and click **Finish** when done.
3. Open VirtualBox. If you see a warning about an inaccessible image file, click **Ignore** — this is expected on first launch.
4. Click **New** to create a virtual machine. Give it a name (typing a recognizable name like "Lubuntu" often auto-detects the Type and Version fields); click **Next**.
5. On the Hardware screen, accept the default memory and processor allocation and click **Next**. On the Virtual Hard Drive screen, leave **Create A Virtual Hard Disk Now** selected and click **Next**, then click **Finish** on the summary screen.
6. With your new VM selected in the left-hand list, click **Settings → Storage**. Under the storage controller, click the empty disc icon, then click the disc-with-arrow icon on the right side and choose **Choose/Create A Virtual Optical Disk**. Browse to your downloaded Linux ISO, select it, and click **Choose**. Click **OK** to return to the main VirtualBox window.
7. With your VM highlighted, click the green **Start** arrow. This boots a live session of the Linux ISO. If you get a "not bootable" error, use the dropdown at the bottom of the error message to point back to your ISO file and retry.
8. Once the live session loads, double-click the **Install** icon on the desktop and proceed through the installer (language, location, keyboard layout). When you reach the installation-type screen, choose the **Erase Disk** option — this only affects the virtual disk you created in step 5, not your real hard drive. Continue with the default options through the rest of the installer, then select **Restart Now** when installation completes.
9. Once the guest OS boots to its desktop, open its equivalent of System Settings or About This PC and record how much RAM and disk space the guest OS reports as available to it.
10. Write two to three sentences explaining, based on this chapter, why the host machine needed roughly 8 GB of total RAM to comfortably run this lab, even though the guest OS itself might only report 2–4 GB available to it.

**Expected Result:** VirtualBox installed successfully, a new virtual machine created with its own virtual hard disk, a Linux guest OS fully installed and rebooted into its own desktop, and a short written explanation connecting the RAM math to this chapter's host-plus-guest resource requirements.