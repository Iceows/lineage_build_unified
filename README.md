
## Building PHH-based LineageOS GSIs ##

To get started with building LineageOS GSI, you'll need to get familiar with [Git and Repo](https://source.android.com/source/using-repo.html), and set up your environment by referring to [LineageOS Wiki](https://wiki.lineageos.org/devices/redfin/build) (mainly "Install the build packages") and [How to build a GSI](https://github.com/phhusson/treble_experimentations/wiki/How-to-build-a-GSI%3F).

First, open a new Terminal window, which defaults to your home directory.  Clone the modified treble_experimentations repo there:

    git clone https://github.com/iceows/treble_experimentations

Create a new working directory for your LineageOS build and navigate to it:

    mkdir lineage-18.x-build-gsi; cd lineage-18.x-build-gsi

Initialize your LineageOS workspace:

    repo init -u https://github.com/LineageOS/android.git -b lineage-18.1

Clone both this and the patches repos:

    git clone https://github.com/iceows/lineage_build_unified lineage_build_unified -b lineage-18.1
    git clone https://github.com/iceows/lineage_patches_unified lineage_patches_unified -b lineage-18.1

Finally, start the build script :

    bash lineage_build_unified/buildbot_unified.sh treble 64B
    
or to include AndyCG patch
    bash lineage_build_unified/buildbot_unified.sh treble personal iceows 64B

or to include also Iceows patch
    bash lineage_build_unified/buildbot_unified.sh treble personal iceows 64B

Be sure to update the cloned repos from time to time!

---

A-only targets afor Huawei hi6250 re generated from AB images instead of source-built - refer to [sas-creator](https://github.com/iceows/huawei-creator).

	sudo ./run-huawei-full-opt.sh "myimage.img"  "LeaOS" 

---

This script is also used to make builds without sync repo. To do so add nosync in the command build line.
