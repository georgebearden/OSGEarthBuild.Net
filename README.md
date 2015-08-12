# SharpEarth
osgEarth in C#

SharpEarth is a thin, C++/CLI layer on top of [OpenSceneGraph](https://github.com/openscenegraph/osg) and [osgEarth](https://github.com/gwaldron/osgearth).  

### Building the dependencies
I am considering providing a download to all the prebuilt libraries, but for now the OSG and OSGEarth dependencies need to be built manually following the steps below.  Also, the OSG and OSGEarth websites have great documentation on how to build.

* Install [CMake](http://www.cmake.org/www.cmake.org/download)
* Download [OpenSceneGraph 3-2.2](http://trac.openscenegraph.org/downloads/developer_releases/OpenSceneGraph-3.2.2.zip) and extract OpenSceneGraph-3.2.2.zip to C:\SharpEarth\OpenSceneGraph
* Download [3rdParty Dependencies](http://download.osgvisual.org/3rdParty_VS2013_v120_x86_x64_V9_full.7z) and extract the 3rdParty_VS2013_v120_x86_x64_V9_full\3rdParty_x86_x64\x64 folder to C:\SharpEarth\3rdParty
* Download [OsgEarth-2.7](https://github.com/gwaldron/osgearth/zipball/osgearth-2.7) and extract gwaldron-osgearth-osgearth-2.7-0-g25ce0e1.zip to C:\SharpEarth\OSGEarth

You should have the following folder structure (C:\SharpEarth is where I am putting everything, feel free to choose your own place)
* C:\SharpEarth
    * 3rdParty
        * bin
        * data
        * include
        * lib
        * ssl
    * OpenSceneGraph
        * applications
        * CMakeModules
        * doc
        * examples
        * include
        * packaging
        * PlatformSpecifics
        * src
    * OSGEarth
        * CMakeModules
        * data
        * docs
        * src
        * tests
