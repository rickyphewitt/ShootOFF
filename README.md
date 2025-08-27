ShootOFF [![Build Status](https://travis-ci.org/phrack/ShootOFF.svg?branch=master)](https://travis-ci.org/phrack/ShootOFF)
========

**Please visit our homepage at http://www.shootoffapp.com**

**There you will find the latest version of ShootOFF, Youtube videos, and more information.**

You can find additional information about using ShootOFF on the wiki: https://github.com/phrack/ShootOFF/wiki

=====

*Report a bug: Through this github or Reddit: https://www.reddit.com/r/ShootOFF/*

You can email us if you do not want to use the above two options. Please be aware that our volunteer-only efforts often get overwhelmed by the number of emails: project.shootoff@gmail.com.


### Developers

An open source, cross-platform framework to enhance laser dry fire training. The Shoot: Open Fire Framework (ShootOFF for short) runs on Linux, Mac, and Windows out of the box.

To work with the ShootOFF source code you will need, at a minimum:

* JDK 8 with JavaFX -- the easiest way to get this is to install the Oracle version of the JDK; OpenJDK does have the JavaFX source code, but the process to get a working JDK with it at the moment is time consuming. The minimum version for ShootOFF is 8u40. Any earlier version will not have the Dialog class (https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/Dialog.html), which ShootOFF uses for alerts
  * Sign in and download jdk
  * Extract to where your java is normally, linux /usr/lib/jvm/<java version>
  * create sybolic links like here: https://ubuntuhandbook.org/index.php/2022/03/install-jdk-18-ubuntu/
  * `sudo update-alternatives --config java` to change it
* OpenJDk 11 
  * Install JDK/JRI
  * Install 64 bit version of libv41 (32 bit if its an old comp)
    * `sudo apt-get install -y libv4l`
    * Then before running the jar load the module, for 22.04 this is installed at the below location
      * `LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libv4l/v4l1compat.so`
      * full command `export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libv4l/v4l1compat.so; java -jar build/libs/ShootOFF.jar`
* Gradle -- ensure the JDK you installed above is the default JDK, otherwise the build script will not be able to find the Ant tasks our build script uses for JavaFX deployment

To use Eclipse, we recommend installing E(fx)clipse and SceneBuilder as well. To generate an importable Eclipse project run: gradle eclipse

To create a runnable JAR file in build/dist (run with $ build/dist/java -jar ShootOFF.jar): gradle fxJar
