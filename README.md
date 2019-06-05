# 1. ZED-jetson
This repositary will guide you to use the Nvidia Jetson nano development kit with the ZED camera to create a 3D map of the surrounding and to be used for navigation.
# 1.1 Jetson nano Installation
The Jetson Nano Developer Kit uses a microSD card as a boot device and for main storage. It’s important to have a card that’s fast and large enough for your projects; the minimum recommended is a 16GB.
## Write Image to the microSD Card
To prepare your microSD card, you’ll need a computer with Internet connection and the ability to read and write SD cards, either via a built-in SD card slot or adapter.

1. Download the [Jetson Nano Developer Kit SD Card Image](https://nvidia.box.com/shared/static/dp7xma0f4jbvttha6xo14km14fztal7o.zip), and note where it was saved on the computer.
2. Write the image to your microSD card by following the instructions below according to the type of computer you are using: Windows, Mac, or Linux. 
### Windows

1.    Download, install, and launch [SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter/) for Windows.
2.    Select card drive
3.    Select “Quick format”
4.    Leave “Volume label” blank
5.    Click “Format” to start formatting, and “Yes” on the warning dialog

#### Use Etcher to write the Jetson Nano Developer Kit SD Card Image to your microSD card

   1. Download, install, and launch [Etcher](https://www.balena.io/etcher/).
   2. Click “Select image” and choose the zipped image file downloaded earlier.
   3. Insert your microSD card if not already inserted.
   5. Click “Select drive” and choose the correct device.
   6. Click “Flash!” It will take Etcher about 10-20 minutes to write and validate the image if your microSD card is connected via USB3.
   7. After Etcher finishes, Windows may let you know it doesn’t know how to read the SD Card. Just click Cancel and remove the microSD card.

### LINUX
Type 1: Etcher (follow the same steps a Windows)
Type 2: Terminal.

   Command Line Instructions
   1. Open the Terminal application by pressing Ctrl + Alt + t.
   2. Insert your microSD card, then use a command like this to show which disk device was assigned to it:
      dmesg | tail | awk '$3 == "sd" {print}'
   3. Use this command to write the zipped SD card image to the microSD card:
      /usr/bin/unzip -p ~/Downloads/jetson_nano_devkit_sd_card.zip | sudo /bin/dd of=/dev/sd<x> bs=1M status=progress
      When the dd command finishes, eject the disk device from the command line:
   4. sudo eject /dev/sd<x>
    
    Physically remove microSD card from the computer.

After your microSD card is ready, proceed to Setup your developer kit.

#### First Boot

A green LED next to the Micro-USB connector will light as soon as the developer kit powers on. When you boot the first time, the Jetson Nano Developer Kit will take you through some initial setup, including:

    Review and accept NVIDIA Jetson software EULA
    Select system language, keyboard layout, and time zone
    Create username, password, and computer name Log in
#### You can now use the jetson nano same as raspberry pi or an ubuntu machine

# ZED
The ZED is a camera with dual lenses. It captures high-definition 3D video with a wide field of view and outputs two synchronized left and right video streams in side-by-side format on USB 3.0.

## Connect your camera

Unpack your camera, plug the camera in a USB 3.0 port and go to the next step. The ZED is a UVC compliant camera so it should be automatically recognized by your computer.

## Download and install the ZED SDK

The ZED SDK is available for Windows, Linux and Nvidia Jetson boards. It contains all the libraries that powers your camera along with tools that let you test its features and settings.

### Windows

Download the [ZED SDK](https://www.stereolabs.com/developers/release/)for Windows and run the installer.

### Linux

On Linux, download the [ZED SDK](https://www.stereolabs.com/developers/release/) for Linux and launch the .run file from a terminal.

 ```
 chmod +x ZED_SDK_Linux_*.run
 ./ZED_SDK_Linux_*.run
 ```
 After the installation, download CUDA from NVIDIA website and install it on your system. Restart you computer to complete the installation.

### Run the ZED Explorer

The ZED Explorer is an application for ZED live preview and recording. It lets you change video resolution, aspect ratio, camera parameters, and capture high resolution snapshots and 3D video.

If the ZED is recognized by your computer, you’ll see the 3D video from your camera.

#### How to run it?
##### Windows
   Windows: C:\Program Files (x86)\ZED SDK\tools\ZED Explorer.exe
   Linux (Ubuntu) : /usr/local/zed/tools/ZED Explorer
   
   ** In linux make the file executable by renaming the file to ZED_Explorer
   ```
   chmod +x ZED_Explorer
   ```
   ** to run it
   ```
   ./ZED_Explorer
   ```
   
Your 3D camera will run with the ZED Explorer window.
