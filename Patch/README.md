# CAUTION: ONLY USE THIS ON BC250s THAT HAVE BEEN VERIFIED TO HAVE ALL 8 CPU CORES FUNCTIONAL VIA ANOTHER METHOD FIRST

Credit to https://github.com/rw-r-r-0644 for creating an implementation of the core unlock, which I used as a reference when making the core unlock driver

- Rescue Mei

# Using the Patch

1) Ensure xdelta3 and md5sum are available
2) Place BC250_3.00_CHIPSETMENU.ROM in the Patch directory.
3) Run ApplyDeltaPatch.sh, which will generate the final BC250 bios rom file.
4) Verify the MD5 hash matches the following:

- d298267029fbbe9d29b0bfa0db5fbf9e  BC250_3.00_CHIPSETMENU.ROM
- a38bb7cd2df24b8e7d9cbb558bf26a2c  BC250_3.00_MeiMeiDXEv2.1.ROM
- 63150596c7919a6314215be07479ee34  BC250_3.00_CHIPSETMENU-to-BC250_3.00_MeiMeiDXEv2.1.xdelta

5) If the hashes match, you should be set to flash it to the BC250 via whichever method you prefer.