# Ogrebullet for Linux

I have created this repository for my personal use and convenience. For a repository that builds with CMake, use [Alexey Knyshev's repository]

This code has been updated to work with Bullet versions 2.81 and newer and fixed to install on Ubuntu linux with ease. I have not tested it with other Linux distros.

This code was forked from original [SVN repository at Sourceforge] with Ogreaddons' revision 2988.

## Install instructions on Ubuntu Linux
#### 1. Install dependencies:
```sh
$ sudo apt-get install cmake autoconf automake libtool libgl1-mesa-dev freeglut3-dev
```
#### 2. Download and install Bullet 
Download from official repository: https://github.com/bulletphysics/bullet3 and run from Bullet source root:
```sh
$ cmake . -G "Unix Makefiles" -DINSTALL_EXTRA_LIBS=TRUE -DCMAKE_CXX_FLAGS="-fPIC" -DCMAKE_C_FLAGS="-fPIC"
$ make
$ sudo make install
```
#### 3. Compile and install Ogrebullet
Run these commands in the source root of this repository:
```sh
$ ./autogen.sh
$ CXXFLAGS=-I/usr/local/include/bullet/ConvexDecomposition ./configure
$ make
$ sudo make install
$ sudo ldconfig
```

License
----
MIT

[Alexey Knyshev's repository]:http://bitbucket.org/alexeyknyshev/ogrebullet
[SVN repository at Sourceforge]: http://sourceforge.net/p/ogreaddons/code/HEAD/tree/trunk/ogrebullet/
