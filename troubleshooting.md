# OKVIS Build Troubleshooting #

Code builds succesfully with g++ v6. To change compiler to g++ v6 follow [this](https://linuxconfig.org/how-to-switch-between-multiple-gcc-and-g-compiler-versions-on-ubuntu-20-04-lts-focal-fossa)
You might need to add "*deb http://dk.archive.ubuntu.com/ubuntu/ bionic main universe*" to your "/etc/apt/sources.list" to install g++ v6.

OKVIS dependancy BRISK is installed during CMake process, and is developed for OpenCV v3. Hence, initial build always results in an error. To fix, modify file "build/okvis_ros/okvis/brisk/src/brisk_external/src/demo-free.cc" by replacing all "*CV_BGR2GRAY*" with: "*cv::COLOR_BGR2GRAY*"
If performing a clean build in the future, remember to change this again.
