# Some tricks for os installation on apple hardware

The tricks below come to me from different experiences installing linux systems on my old macbook for development use.

## custom EFI

It's not a problem to install a linux os with the default mac EFI, but it can be more practical to install a specific one for more control and fine tuning.

[rEFInd installation](http://www.rodsbooks.com/refind/installing.html)

## Use rEFInd to start integrated graphics on macbook

The problem is : When yous start a system diffrent than macOS, the integrated GPU stays offline becaus it is deactivated by the EFI wich disable functionalities depending on the os started.

rEFInd provides a simple option to trick the EFI. So the EFI will think that macOS start, but there's an other system starting, thus the integrated GPU will start.

1. Install rEFInd : see first section of this file.
2. Add the `spoof_osx_version` on the `refind.conf` file.

> To find the refind.conf file you need to mound your EFI partition on you active system. For example `mount /dev/sda1 /boot/efi`.

Additional resources :
- [0xbb/gpu-switch](https://github.com/0xbb/gpu-switch)
- [rEFInd config](http://www.rodsbooks.com/refind/configfile.html)
