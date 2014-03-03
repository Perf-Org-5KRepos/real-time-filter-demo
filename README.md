Real-time Filter Demo
=====================

A Nokia example application demonstrating the use of the Nokia Imaging SDK for
real-time image effects. The effects are applied to the stream received from the
camera and shown in the viewfinder. This app does not support capturing photos. 

This example application is hosted in GitHub:
https://github.com/nokia-developer/real-time-filter-demo

For more information on implementation visit Nokia Lumia Developer's Library:
http://developer.nokia.com/Resources/Library/Lumia/nokia-imaging-sdk/sample-projects/real-time-filter-demo.html


1. Prerequisites
-------------------------------------------------------------------------------
For Windows Phone version
* C# basics
* Windows 8
* Microsoft Visual Studio Express for Windows Phone 2012
* Windows Phone 8 device

For Windows version
* C# basics
* Windows 8.1
* Microsoft Visual Studio 2013 Express for Windows Store
* Windows 8.1 device with a webcam

2. Project structure and implementation
-------------------------------------------------------------------------------

The example consists basically of three key classes. The main page is your
typical phone application page implemented by a XAML file and a C# counterpart.
The main page implements the application UI including the `MediaElement` which
displays the camera viewfinder with an effect. The `MainPage` class also owns
the instances of the two other key classes: `CameraStreamSource` and
`NokiaImageEditingSDKEffects`. The `CameraStreamSource`, derived from
`MediaStreamSource`, provides the camera data. The `NokiaImageEditingSDKEffects`
implements all the effects of the application. 

Windows version has all the camera related functionality in the `MainPage` class, 
in the MainPage.Camera.cs file. Windows version uses `CameraPreviewImageSource` 
instead of `CameraStreamSource` to get the preview images from the camera. The
effects have been added to custom `FilterListObject` list, from where they are 
created by reflection on the fly. This step is made to demonstrate how you can
create the filters on demand, otherwise the developer could have just created 
them directly and put to the list.


3. Compatibility
-------------------------------------------------------------------------------

Windows Phone 8. Tested to work on Nokia Lumia 920 and Nokia Lumia 520.
Developed with Microsoft Visual Studio Express for Windows Phone 2012.

Windows 8.1. Tested on Lumia 2520 and Surface 2.


3.2 Known Issues
----------------

None.


4. Building, installing, and running the application
-------------------------------------------------------------------------------

4.1 Preparations for Windows Phone
----------------------------------

Make sure you have the following installed:

* Windows 8
* Windows Phone SDK 8.0
* Nuget 2.7+

4.2 Using the WINDOWS PHONE 8 SDK
---------------------------------

1. Open the SLN file:
   File > Open Project, select the solution (.sln postfix) file
2. Select the target 'Device' and platform 'ARM'.
3. Press F5 to build the project and run it on device.

If the project does not compile on the first attempt it's possible that you
did not have the required packages yet. With Nuget 2.7 or later the missing
packages are fetched automatically when build process is invoked, so try
building again. If some packages cannot be found there should be an
error stating this in the Output panel in Visual Studio Express.

For more information on deploying and testing applications see:
http://msdn.microsoft.com/en-us/library/gg588378%28v=vs.92%29.aspx

4.3 Preparations for Windows
----------------------------
Make sure you have the following installed:

* Windows 8.1
* Nuget 2.7+


5. License
-------------------------------------------------------------------------------

See the license text file
https://github.com/nokia-developer/real-time-filter-demo/blob/master/Licence.txt


6. Version history
-------------------------------------------------------------------------------

* 1.2.0.0: Fourth public release of Real-time Filter Demo
  - Updated to the latest Nokia Imaging SDK version 1.1.177

* 1.1.0.0: Third public release of Real-time Filter Demo
  - Updated to use the latest Nokia Imaging SDK
  - Added custom made inverted grayscale filter
  - Using Nuget Package Restore for external libraries
  - Overall code refactoring and productization

* 1.0.1.0: Second public release of Real-time Filter Demo
  - Fix: MediaElement did not release the camera handle
  
* 1.0.0.0: First public release of Real-time Filter Demo
