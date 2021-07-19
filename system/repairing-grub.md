You have messed up with your system and now you can't boot into your favorite OS or you can't boot at all? Don't worry, I got your back future myself! Let's start:

  1. Find some way to get into terminal. If you can't boot at all, go and prepare a live bootable media. If you can boot, continue with the second step.
  2. Now you are inside your beautiful terminal, (well it may not be beautiful for your eyes but this is a real, naked terminal. Feel the power that it gives you. It's fucking perfect!) you need to know that the following commands are dangerous. Be careful while executing them. This might be your last chance, don't mess this up!
  3. Run `sudo fdisk -l` to know which partition your system is in. Let's assume it is `/dev/sda5`
  4. `mkdir mount_dir`
  5. `sudo mount /dev/sda5 ./mount_dir`
  6. [Optional] You can check mount_dir to see if you mounted the correct partition. `cd mount_dir; ls`
  7. `sudo grub-mkconfig -o /boot/grub/grub.cfg`

And you should be done. If it didn't work, you can check if you have `os-prober` **installed** and **enabled** on your system. `cat /etc/default/grub` and there should be a line like `GRUB_DISABLE_OS_PROBER="false"`

Reboot and thank me later! 

Wait what? You still couldn't manage to repair?! Damn, I can feel you are about to shit on your pants rn. Anyway, here are some links that is literally the top results when I search for this: [click](https://askubuntu.com/questions/88384/how-can-i-repair-grub-how-to-get-ubuntu-back-after-installing-windows)<sup>1</sup> and [click](https://askubuntu.com/questions/143667/boot-error-no-such-device-grub-rescue?noredirect=1&lq=1). Good luck!

<sup>1</sup>: Of course I didn't install W*ndows and I hope you did not either! The other question was closed as duplicate of this one so I included the link just in case.
