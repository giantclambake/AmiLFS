# AmiLFS
A Linux From Scratch based instance for Amiga emulation on x86 hardware ~ inspired by the AmiDeb instance!

This project was inspired by the Debian linux based OS instance known as 'AmiDeb'

You can read all about that, and even try it if you wish, visit it's website --> https://amiga.vk3heg.net/ 

A way of looking at this, is from the 'turn a PC into a Amiga' (via emulation) viewpoint, and I found the minimum spec the host machine needed to be, was somewhere near intel P4 @ 2.8MHz with 512MB of ram, which utilized roughly 160% of cpu time spread across the two cores. The fs-uae emulation was running acceptably on this level of ix86 machine. 

The creator of AmiDeb affirmed, there was a niche target machine, that one could install AmiDeb on, and ostensibly have a small footprint machine as akin to a set-top-box Amiga emulator, as that machine's only purpose in life, and if the right hardware was utilized, you might be able to enjoy Amiga gaming on a teevee display instead of a computer monitor.

That machine, would be one of a plethora of 'Thin Client' type computers, both new and rather cheap 2ndhand devices, ex-of business/POS operations. Although other platforms exist that can achieve the same ends, there wouldn't be many that could claim that in a way, AmiDeb helps find use for this type of x86 hardware in the 2ndhand market, as it were recycling the machine by repurposing it to be a specific linux based 'appliance' ...ie; be that an Amiga emulator 'games' box, or one that's used with Amiga Workbench, or perhaps AROS.

I raised the conjecture on the EAB forum, that perhaps Debian wasn't quite the right choice for a dedicated, targeted installation. That is to say, it likely is the very best choice that's going to work for most all x86/x86_64, either in a temporary (USB boot) guise, or install to harddrive scenarios. Further, I speculated that a Lunux From Scratch build, may be more performant when it came to the dedicated task of just doing Amiga emulation, and there very really is only one way to find out -- do it ; here I am =)

I did the $LFS thang back in the early 2000's ; I pretty much only used my own builds for general use, and iirc it was somewhere around 2012 I noticed Debian had started to 'come of age' as it were, so I adopted it as my linux distro of choice, and slid into mainstream, and regaining for time in life ; Debian was finally out of puberty 8)

Reading the LFS book, let alone finding/taking the time to do it, is not everybody's cup of tea. Whilst I really do obtrude upon those interested in linux systems to do the LFS thang at least once in their life, I know it's a non-trivial task to accomplish. 

To that end, there are 3 junctures in such a LFS based build process, that represent the 3 main stage positions...end of one chapter, and the beginning of another. Those points occur at the end of the toolchain build, the end of the base system build, and at the end of userspace software building. 

This build follows version r11.2-314 of the LFS book + Errata + 1 diversion of linux kernel version used, I chose a 5series instead of 6 (patches related). Build host is Debian-11.6-i386 install running on AMD Phenom x4 CPU. This is a 32bit build.

https://drive.google.com/file/d/1w36yl4gJx-i3k1WqJJ1hNqq45Gq1U1Of/view?usp=share_link 

The archive above contains the 32bit LFS toolchain, and all the source archive required to build the base system. As I've already built to boot using this toolchain, I consider it 'tested sane' =)

Usage: This establishes an entry point to the LFS book at https://www.linuxfromscratch.org/lfs/view/stable/chapter07/cleanup.html , section 7.13.3 Restore -- follow the instructions, ensure the $LFS variable is set, and you're good to go if you want to build the base system itself.

Later I'll upload another archive, that establishes an entry point at the beginning of section 10 in the book. This will be a smaller archive, as the build is complete, stripped, and we no longer need all of the source archives nor the toolchain. 

The 3rd stage is building towards the fs-uae target, and most of this building will be done using compiler optimizations in the ateempt to speed up binary/library runtime execution. When the same functionality is achievered wrt the functionality AmiDeb establishes on the same hardware, them I might find out if anything was gained, whether X and fs-uae run any better.

If then comparative testing proves the effort was worth it, then a final cutdown binary archive can be created, perhaps replace many base shell programs with a busybox installation, remove any binaries/libraries not mission critical to the working system. 
