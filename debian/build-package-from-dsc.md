From [Linuxquestions.org][1]

Full procedure to install the package related to a `.dsc` file:

0. Before you begin, note that, besides the `.dsc` file, you must have the corresponding `xxx-orig.tar.xz` and `xxx-debian.tar.xz` files.

1. Install `dpkg-dev` package, if not present in your linux machine

    `sudo apt-get install dpkg-dev`

2. Following command extracts the package into an automatically created directory. Note: the necessary `xxx-orig.tar.xz` and `xxx-debian.tar.xz` files must be in the same directory as the `.dsc` file in order to work properly.

    `dpkg-source -x yourfile.dsc`

      If you get error message concerning the signature, [check this post here][2].

3. To build the package get into the directory that was created in 2nd step and issue this command

    `dpkg-buildpackage -rfakeroot -b`

4. To install the built package issue this command

    `dpkg -i ../yourfile_arch.deb`


  [1]: https://www.linuxquestions.org/questions/linux-newbie-8/how-to-install-dsc-file-in-linux-896928/
  [2]: https://askubuntu.com/questions/56841/gpg-cant-check-signature#198420
