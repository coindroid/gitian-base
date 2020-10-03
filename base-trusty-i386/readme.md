**NOTICE:**
In this image wine was changed to wine1.7-i386, you need change wine -> wine1.7-i386 in your gitian.yml file for correct compiling.


**WIN32 image trusty-i386_win32:** 

    # Pull image from Docker hub
    docker pull coindroid42/gitian-base:trusty-i386_win32
    # change name for gitian
    docker image tag coindroid42/gitian-base:trusty-i386_win32 base-trusty-i386:latest

*was tested with https://github.com/devrandom/gitian-builder/tree/ff8d73dc7d98eb421245fec613275e65386efd92*
