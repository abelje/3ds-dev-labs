# Making the 3ds Coding Environment
As of 12/13/25
## devkitPro
I am taking advantage of prebuilt toolchains from devkitPro to code on the 3ds in a more sophisticated matter. More information on how to use this is updated here:

[devkitpro.org](https://devkitpro.org/wiki/Getting_Started)

I want to install this to my existing WSL Debian distro on my laptop, so I am going to run this commands from the website to set it up:

[devkitPro_pacman](https://devkitpro.org/wiki/devkitPro_pacman)

```
wget https://apt.devkitpro.org/install-devkitpro-pacman
chmod +x ./install-devkitpro-pacman
sudo ./install-devkitpro-pacman
```

### Download 3ds dev kits
I ran this in terminal to download the main development kit from pacman:

```
sudo dkp-pacman -S 3ds-dev
```

I then hit enter to have it install all of the development tools.

### Installing libctru
This library is for the foundation of 3ds homebrew, After looking through the installed programs with the 3ds dev kit command, I found that I already had the library. More information on this library is located here:

[libctru](https://libctru.devkitpro.org/)