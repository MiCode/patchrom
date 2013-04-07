Patchrom
===========

Get Android SDK
----------------

In order to build patchrom project, you must have android sdk installed.(http://developer.android.com/sdk/installing.html)

And add the sdk tools and platform-tools to PATH.

vim .bashrc

export PATH=$PATH:/home/xxx/android-sdk/tools:/home/xxx/anroid-sdk/platform-tools

Getting Started
---------------

To get started with MiCode/patchrom, you'll need to get
familiar with [Git and Repo](http://source.android.com/download/using-repo).

To initialize your local repository using the patchrom trees, use a command like this:

    mkdir patchrom

    cd patchrom

    repo init -u git://github.com/MiCode/patchrom.git -b jellybean

Then to sync up:

    repo sync

Build
--------

Assumed current directory is patchtom and you want to build the ROM for Huawei Honor


     . build/envsetup.sh
     cd honor
     make fullota

After build completed, there will be a fullota.zip under out directory, now you can flash this file into your device.


Porting new device
------------------

Asssumed current directory is patchrom and you want to port miui to a new android device xblade

Prerequiste:
(1) Your device has root privilege or a rooted kernel(preferred)

(2) Your device can flash ZIP from recovery(ext4 or CWM recovery is preferred)

Workflow:

(1) connect your device to PC, ensure adb works

(2) run the following commands

     . build/envsetup.sh

     mkdir xblade

     cd xblade
      
     adb reboot recovery

     ../tools/releasetools/ota_target_from_phone -r (this will generate a stockrom.zip, flash this zip in recovery mode to ensure it works)

     cp ../honor/makefile .(modify the local-zip-file to stockrom.zip, read the comments in makefile)

     make workspace

     make firstpatch (this will add the miui code into framework/android.policy/services.jar, resolve any conflict)

     make fullota

Now you can get your own miui ROM, enjoy it!

