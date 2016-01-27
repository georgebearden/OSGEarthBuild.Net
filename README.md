### Building the dependencies
First, a few notes.
* I am considering providing a download to all the prebuilt libraries, but for now the OSG and OSGEarth dependencies need to be built manually following the steps below.  
* OSG and OSGEarth websites have great documentation on how to build.
* An automated build process is being created to avoid having to manually do the steps below... It is coming soon.
* The build is based on Visual Studio 2013, and is 64 bit

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

Run CMake, Set "Where is the source code" to "C:/SharpEarth/OpenSceneGraph", Set "Where to build the binaries" to "C:/SharpEarth/OpenSceneGraph/Build", click Configure, Choose "Visual Studio 12 2013 Win64" and Click Finish.  Set the GDAL_LIBRARY_DEBUG value to "C:/SharpEarth/3rdParty/lib/gdal_i.lib" and click Configure again.  Click Generate.

Open "C:\SharpEarth\OpenSceneGraph\Build\OpenSceneGraph.sln" as Administrator in Visual Studio 2013.  Right-click the ALL_BUILD project and choose Build.  This takes about 30 minutes on my machine (a 2014 i7 imac).  Once it is finished, change the configuration to Release and Build the ALL_BUILD project again.  This takes about 30 minutes also...  Lastly, and this is the reason for running as admin, build the Install project under the CMakePredefinedTargets folder for both Debug and Release configurations (Note there are config options in CMake to change the install directory, but I am trying to keep this as simple as possible).  This will install the bin/lib/include folders for OpenSceneGraph to "C:\Program Files\OpenSceneGraph"
