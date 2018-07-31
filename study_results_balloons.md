### 8 - Results Using Balloons and Kites

#### Introduction

When our project was initiated the plan was to use methods that are readily available to anyone and to apply these in ways that do not impose a high barrier in terms of time and materials. 
Farmers are generally very practical regarding the kind of tool they are willing to try in order to solve a 
problem. Most are eager to learn a new method if it helps solve a long-standing issue more efficiently. As an example, crop 
scouting has existed as long as farming has and its methods have changed very little except that what was once done on foot or 
by horse is now done in a pick-up truck. 

![](img/kite_image_rgb.png)
###### Figure 1. RGB image captured with a Delta kite at height of 150ft. Ground control points (in yellow) are visible.

#### Image capture and preparation

With that sentiment in mind we discuss results obtained by experimenting with aerial photography using a kite or a balloon. 
__Figure 3__ is a RGB composite stitched together 'by hand' with the help of ground control points (GCPs) 
spray-painted into the field. Having GCPs in a set of images like this was critical to our 
ability both to stitch together a larger image and to compare image sets over successive days. To support this
process we used an open source software known as [Fiji](https://fiji.sc/). Fiji is an image processing 
package which bundles an incredible variety of plugins to facilitate scientific image analysis.  

To determine the height of a flight we carefully measured and marked the kite's flight line. This set of 
captures was taken at a height of 150ft. Maintaining a steady altitude like this with a kite can be a challenge when the 
wind is variable. 

#### JPEG versus RAW Format

The RAW format captures everything without pre-processing while JPEG does not...

A source of artifact in JPEG images used for spectral index purposes is compression and band distortion. Digital Image Compression (DIC) addresses issues of storage 
and transmission since storage space is at a premium in a consumer-grade camera. For our purposes, image compression 
and band distortion are less features than issues to be corrected. Compression and band distortion occur in the camera during
capture and may impact the ability to utilize _all_ bandwidth data in post-processing. JPEG files are automatically pre-processed in
the camera though exactly how varies from model to model. 
 
While some consumer cameras systems support RAW image formats, RAW images are much larger (a factor when taking many shots during flight). For this reason our results using a consumer camera are based on the JPEG format. How to accurately calibrate for reflectance under changing illuminant conditions while still being limited to JPEG compression for practical reasons is an issue that . 
Another issue is lack of accurate geotagging support in most consumer cameras. While most cameras support 
this feature, in practice we found it to be inconsistent as a reliable source of reference regarding the planar as well 
as vertical positioning of the camera with respect to the field. A hand-held GPS device was used to create the ground
control points but it was not always possible to use geotagging of images to match each capture with a known position 
on the ground. 

Having obtained a set of images we then scripted a process in Fiji to help align, stitch and create the vegetation index.  
   
#### Image Captures
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

![](img/2016_0513_122_rgb.jpg)
![](img/2016_0513_122_ndvi.jpg)
###### Figure 3. NDVI image with reference color LUT. This image was captured with a Delta kite at height of 125ft.
__Figure 3__ is an NDVI index derived from RGB and NIR imagesets using a pair of modified consumer cameras. It was taken 
from a height of about about 125 ft early in the growth season.  

![](img/2016_0513_141_rgb.jpg)
![](img/2016_0513_168_ndvi_color.jpg)
###### Figure 4. NDVI image from 200 ft. Ground resolution is 8-10" ft per pixel.
__Figure 4__ is another NDVI index derived from RGB and NIR image sets using a pair of modified consumer cameras. It was taken 
from a height of about 200 ft.   

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.


![](img/1m-resolution.png)
1 meter per pixel

![](img/3in-resolution.png)
3 inch per pixel

![](img/1in-resolution.png)
~1 inch per pixel (2.7 cm)

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

#### Summary

Early in the project we experimented with various capture systems (automatically-triggered cameras) and suspension methods 
using kites and balloons. The central challenge of an aerial system based on wind alone is variability in the 
control of height and nadir positioning of the camera. Wind can impact the performance of a balloon during flight. 
Additional factors to consider are payload weight and total flight time. 

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

###### References

[TBD]

![](img/farmera.png) 