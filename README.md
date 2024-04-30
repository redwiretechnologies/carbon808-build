# carbon808-build
A package of the submodules to build custom openembedded images for the RWT Carbon  SDR Development Kit
This is currently nuilt on the kirkstone branch of OpenEmbedded/Yocto

OpenEmbedded allows the creation of custom linux distributions for embedded systems. It is a collection of git repositories known as layers each of which provides recipes to build software packages as well as configuration information.

Information about the branch names is available at https://wiki.yoctoproject.org/wiki/Releases. Helpful articles about working with GNUradio and Openembedded are at: http://www.opensdr.com/categories/.


Install the Xilinx Vitis tools for the 2021.2 release
The files should be installed in the /opt/Xilinx default directory structure or the local.conf will need to be updated to point to the correct directory

Getting Started
Clone the git repository:

$ git clone https://github.com/redwiretechnologies/carbon808-build.git -b kirkstone

Change Directory
$cd carbon808-build

Update the submodules:

$ git submodule update --init

Initialize the build system:

For Just a Carbon808 SDR:

$ TEMPLATECONF=\`pwd\`/meta-rwt-carbon808/conf/ source ./poky/oe-init-build-env ./build

For a Carbon808 with a CARP backpack:

$ TEMPLATECONF=\`pwd\`/meta-rwt-carbon808-carp/conf/ source ./poky/oe-init-build-env ./build

Select the MACHINE to build for:

Build an image:

$ bitbake rwt-sdr-image -k

To update the submodules to the latest versions:

$ git submodule update --remote

Running this command may update repos which will trigger a near full rebuid of the distrubion.  Updating the repos helps to fix bugs and also fix CVEs in the system
