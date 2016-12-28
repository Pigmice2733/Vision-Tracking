Vision Tracking Project
========================

This project currently includes everything you need to get started
with *vision tracking* on a [Raspberry Pi computer][1] with a direct-port
[camera module][2].


Project Contents
----------------

This project includes an operating system image for Raspberry Pi 3
(Raspbian) with everything needed to do vision tracking for the robot
all pre-built, libraries compiled and configured.  This includes:

  • Vision libraries using OpenCV 3 with Python 3 wrapper

  • RTSP server for live streaming from Raspberry PI camera to your
    remote PC.  (For debugging, quite handy to have when the Pi &
    camera are attached to the robot and you need to see what the
    robot is seeing but not needed when you are working with the Pi on
    the bench with monitor and keyboard connected to it)

  • Libraries for talking to the roboRIO, driving the robot using roboRIO, etc.

Once booted on your Raspberry Pi, this will give you an environment
with sample code.  The sample code is written in Pythin, but if you
are not familiar with Python, it will be good to pick up that online
(eg. www.codeacademy.com).  It is a good language to have under your
belt.  It is extremely popular, heavily-used for prototyping, simple
to learn yet very powerful.

**Note:** For the image processing samples, at this stage, please
don’t worry too much about how the particular algorithm in the library
works.  Focus on learning how to use it to make it to do what you want
it to do (what knobs to turn, etc.).  Learning how to use a particular
algorithm or filter provided by the OpenCV library correctly is
challenging in itself.

  * `test_image.py`: demonstrates grabbing an image from the camera
    and showing it on the debug window.

  * `test_video.py`: demonstrates getting a video stream into your
    code as a stream of images that you can process.  Display live
    video in a debug window.

  * `object_movement.py`: demonstrates how to track a single color
    object (green in my sample), illustrates the creation of mask for
    the color green, finding the contours and the center of what is
    being tracked.

  * `bunny_track.py`: demonstrates how to track of an arbitrary
    object.  In this example, you will need to press `i`, then select
    (by mouse clicking) four corners of what you need to track from
    the still image, then hit any key after that to start tracking
    what you selected.

  * `edges.py`: this one was inspired by Ron’s suggestion Tuesday that
    it would be good to track bumpers of other robots, possibly to
    fire the Nerf gun at them.  It demonstrates a simple example of
    one way to track the bumpers of another robot.  It uses a very
    classic edge detection algorithm called Canny edge detector, which
    does not rely on color or shapes of objects in an image.  Canny
    detector has always been my goto algorithm of all sorts of
    different things in the past.


Requirements
------------

For this project, you will need the following:

  * [Raspberry Pi][b1]
  * [Camera Module][b2]
  * [2.1 Amp USB power adapter][b4] with a MicroUSB plug
  * [MicroSD memory][b3] with at least 16Gb size (64Gb is preferable)
  * HDMI monitor and cable or a VGA monitor with a VGA-to-HDMI converter cable
  * Keyboard and mouse

If you would like one of these at home, they can all be purchased on
Amazon and [other locations][b5].


Creating a RPi Image
--------------------

Instructions for creating a bootable SD Card using Vision Tracking Pi
boot OS image and using the sample code.

* Download and install Win32DiskImager from this location:
  https://sourceforge.net/projects/win32diskimager/

* Get the Pi image for vision tracking from this location and save it your PC
  `https://github.com/Pigmice2733/Vision-Tracking/tree/master/rpi3_images/vision_tracking.img`

* Format and insert a 32GB or larger SD card into your laptop.

* Run `Win32DiskImager` application you installed above.

* Browse to the location of the Pi image file that you downloaded from Pigmice GitHub.

* Follow these steps to create a bootable SD using the Pi image:
  ![screen-shot](http://i.imgur.com/nThuBNI.png)

* After the Pi desktop has booted up, run Geany.  Geany is an editor that
  works great for writing Python code.  You should see all the samples we've
  developed. You can [download Geany][3] for your computer.


Running the Samples
-------------------

To run the example, go into **Terminal** (This is the command-prompt),
by clicking on the black square icon on the top bar in Pi desktop.

Commands that you need to type in are in fixed-width font.

Begin by typing:

    workon cv3<enter>

This configures the environment for running OpenCV3 and Python3
libraries and shared files.

While you edit the code with Geany, you *run* the code in
**Terminal**. For instance, to run the `test_image` code, you would
type the following into the **Terminal**:

    python test_image.py

(A shortcut is to use the `Tab` key to complete what you start to
type. For instance, if you type `py` and then press the `Tab` key, it
will expand it to `python`. This technique works for code too, for
when you type `tes` and press `Tab`, it will expand it to `test_`. It
won't expand it to `test_image.py` because there are multiple files
that begin with `test_`, so at this point, you could type an `i`, and
then when you press `Tab`, it will expand it to the full
filename. (You may have to play around with this for a bit.)



  [1]: http://www.raspberrypi.org
  [2]: https://www.raspberrypi.org/products/camera-module/
  [3]: https://www.geany.org/Download/Releases#windowsBinaries
  [b1]: https://www.amazon.com/Raspberry-Pi-RASP-PI-3-Model-Motherboard/dp/B01CD5VC92
  [b2]: https://www.amazon.com/Raspberry-Pi-Camera-Module-Megapixel/dp/B01ER2SKFS
  [b3]: https://www.amazon.com/dp/B010Q588D4
  [b4]: https://www.amazon.com/Smraza-Starter-Raspberry-Supply-Heatsinks/dp/B01I1OESI6
  [b5]: http://www.mcmelectronics.com/product/RASPBERRY-PI-83-16566RK-/83-16566RK
