# SUPERSEDED: See the V3 here

https://github.com/RescueMei/BC250-DXEv3-BIOSMOD

# BC250-DXEv2-BIOSMOD
Central repo for the v2.1 of my bios patch, including three DXE drivers for CPU core unlock, ACPI injection, and auto cold boot!

Drivers used:

- https://github.com/RescueMei/BC250-DXEv2-SMU-Core-Unlock
- https://github.com/RescueMei/BC250-DXEv2-ACPI-AUTOINJECT
- https://github.com/RescueMei/BC250-DXEv2-COLD-BOOT

# CAUTION: ONLY USE THIS ON BC250s THAT HAVE BEEN VERIFIED TO HAVE ALL 8 CPU CORES FUNCTIONAL VIA ANOTHER METHOD FIRST

Credit to https://github.com/rw-r-r-0644 for creating an implementation of the core unlock, which I used as a reference when making the core unlock dxe driver

## For how to use the patch to apply to the BC250_3.00_CHIPSETMENU.ROM BIOS, please see the bottom of this readme

# Why DXE Drivers?

This is so they can run before the OS to perform their tasks, and so they can perform them quickly. 

The Core Unlock driver can perform the smu exploit much faster than other methods of performing it at boot due to how early the DXE driver executes. 

The ACPI driver injects an appropriate ACPI table so it is already present for the OS to use for power management, without requiring the OS to have a separate method to load the table on its own outside of what is presented to it by the bios.

As DXE Drivers in the BIOS, they are unaffected by reinstallations of operating systems or changes to scripts. 

They are configured in "DXE Driver Configuration" under the Advanced settings within the bios.


# Using the Patch

1) Ensure xdelta3 and md5sum are available
2) Place BC250_3.00_CHIPSETMENU.ROM in the Patch directory.
3) Run ApplyDeltaPatch.sh, which will generate the final BC250 bios rom file.
4) Verify the MD5 hash matches the following:

- d298267029fbbe9d29b0bfa0db5fbf9e  BC250_3.00_CHIPSETMENU.ROM
- a38bb7cd2df24b8e7d9cbb558bf26a2c  BC250_3.00_MeiMeiDXEv2.1.ROM
- 63150596c7919a6314215be07479ee34  BC250_3.00_CHIPSETMENU-to-BC250_3.00_MeiMeiDXEv2.1.xdelta

5) If the hashes match, you should be set to flash it to the BC250 via whichever method you prefer.
