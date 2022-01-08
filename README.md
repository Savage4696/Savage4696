- 👋 Hi, I’m @Savage4696
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Savage4696/Savage4696 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
I've Worked On Kali Linux Build.
## Kali-ARM Build-Script

Kali Linux ARM build-scripts.

These are the same build scripts that we use to generate the pre-generated official Kali Linux ARM images, found here: https://www.kali.org/get-kali/

There are additional scripts included in this repository, supporting more devices, but these will need to be built in order for them to be used.

For more information, please see: https://www.kali.org/docs/arm/

- - -

### Building

- These scripts are tested on Kali Linux arm64, x64 and x86 installations only _(I **recommend x64**)_
- Make sure you run the `./common.d/build_deps.sh` script before trying to build an image, as this installs all required dependencies
- You will need at **least 8GB of RAM or use SWAP file**

An example workflow to build a _[Raspberry Pi 4](https://www.kali.org/docs/arm/raspberry-pi-4/) Kali Linux image_ would look like:

```
cd ~/
git clone https://gitlab.com/kalilinux/build-scripts/kali-arm
cd ~/kali-arm/
sudo ./common.d/build_deps.sh
sudo ./rpi.sh
```

- Depending on your system hardware & network connectivity, will depend on how long it will take to build _(4 core CPU, 8GB RAM, SSD inside a VM takes using a [local repo](https://www.kali.org/docs/community/setting-up-a-kali-linux-mirror/) about 100 minutes per script)_
- On x64 systems, after the script finishes running, you will have an image files located in `~/kali-arm/images/` called `kali-linux-2021.3-rpi-armhf.img.xz`
- On x86 systems, as they do not have enough RAM to compress the image, after the script finishes running, you will have an image file located in `~/kali-arm/images/` called `kali-linux-2021.3-rpi-armhf.img`
  - _Should you want to try and shrink the file to make it easier to distribute, you will need to use **your own preferred compression**_.

- - -

### Help

On any build script, add `--help`. Example:

```
$ ./rpi.sh --help
 Usage commands:
# Architectures (arm64, armel, armhf)
