TWRP for SM-T295

TWRP Setup

    mkdir twrp
    install git (fedora: sudo dnf install git*)
    mkdir ~/bin && curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo
    cd twrp
    repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0 (follow directions on screen)
    create local_manifests folder in .repo (cd .repo 
    mkdir local_manifests;
    cd local_manifests
    copy the roomservice.xml contents to ~/twrp/device/samsung/gto/roomservice.xml
    cd ~/twrp
    repo sync (will take awhile to sync) maybe go have a coffee somwhere

TWRP Build

    cd twrp
    move kernel folder to kernel.bak (do not need this folder) ex: mv kernel kernel.bak
    type: source ./build/envsetup.sh
    type: lunch
    select omni_gto-eng
    type: mka recoveryimage

If successful, recovery.img is in out/target/product/gto 
    Copy recovery.img to your device

TWRP Install

    Go to play store and install Official TWRP Manager
    Open Official TWRP Manager
    Select Flash Recovery
    Select recovery.img on your device
    Select Flash Recovery

After flash, shutdown device. Press Vol-Up + Pwr keys You should get into TWRP Recovery

You should get into TWRP Recovery

