# What is this?
This is a package for use on Arch linux to install an existing download of the Spine 2D animation software by esoteric software. This package is for use with the Arch linux distribution.

# What does it do?
Spine can be downloaded and run in a straight-forward manner without needing an installer at all. This exists purely for convenience and does the following:
 * Unzip the tarball you downloaded from esoteric software (trial or full version)
 * Create a symlink named either 'spine' or 'spine-trial' respectively which allows for convenient launching from the command line
 * Add a .desktop file to /usr/share/applications for integration into common desktop environments.
 * Add a simple icon so you can have pretty desktop shortcuts and the likes.

# How to use it
The PKGBUILD can be built using the makepkg utility on arch linux as documented on the Arch wiki.

## Dependencies
Spine uses Java, but fear not, it brings it's own JRE with it inside the tarball you download. No need to install java on your system. It does make use of some graphics APIs and requires xorg as well as some opengl. Additional runtimes, projects might have other special requirements. All i focussed on here was installation of the tarball from the website. For questions about dependencies please refer to the esoteric software website and community.

## Prerequisites: spinetar
The only special part with this PKGBUILD is the 'spinetar' variable, which you *must* set before attempting to build the package.

Only Spine trial builds can be downloaded via public, well-known URLs. Those are of little use to anyone other than people trialing it, since you cannot easily upgrade the installed trial to a pro version. Full version tarballs differ in content and are provided to license owners ONLY via custom download URLs. Therefor this packaging script cannot assume a URL for the tarball other than for the trial builds at the time of writing. As it will be mostly full version owners who are interested in this package (citation needed), I decided to make it mandatory to download the tarball via your custom link and set it's path in the PKGBUILD file using a text editor before attempting to install.

See the PKGBUILD file for details on setting the 'spinetar' variable.

## Using makepkg
As documented in the arch wiki, you can use makepkg to create a pacman package from these scripts. The steps are effectively
 * download spine for linux and your architecture (32/64 bits)
  * either full version via your license email *or* trial version from the spine website
 * download these scripts somewhere on your system
 * edit PKGBUILD and set 'spinevar' variable to the path to your spine tarball (full or trial version, doesn't matter)
 * advanced archers might want to change other things in the script, such as install directories etc.
 * run 'makepkg'
 * install the resulting package (.xz) using pacman (see Arch wiki for details)

## Using yaourt
Yaourt is a popular frontend to install this type of package. It basically does the above but through a slightly more comfortable interface (arguably).

This script works just fine through yaourt but remember to edit the PKGBUILD file when prompted and to set the 'spinevar' variable as described above. The packaging step will fail otherwise.

# License
The source for this installer is licensed as described in LICENSE, but keep in mind that Spine is proprietary software owned by esoteric software and is licensed completely on it's own, under it's own conditions etc.

# Spine support, documentation, licensing etc.
You can find more details on Spine and it's licensing at the esoteric software website: <http://www.esotericsoftware.com>
