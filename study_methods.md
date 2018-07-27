### Study Goals and Methods

#### Introduction

This section provides a description of the various tools and methods used to generate and assess multi-spectral data in 
sugar cane. We also describe some of the challenges faced in gathering such data. Throughout this study our objective 
has been to test the viability of low-cost methods for acquiring and processing aerial multi-spectral data. 

Our primary goal was to determine to what extent low-cost aerial multi-spectral data can be correlated with variable 
nitrogen (N) rates applied to sugarcane. NDVI is a popular vegetation index which has been shown to be effective in 
predicting crop yield potentials (YP) in wheat, sorghum and other plant species. __[fn]__ Yet acquisition and interpretation 
of these data using traditional methods is expensive, error prone, and often beyond reach of most Louisiana sugar cane growers.

The systems we proposed at the outset of our study were both affordable and accessible. How accurately they might correlate 
NDVI other vegetation indices to known nitrogen (N) rates was unknown. Over the course of our study a third option became 
tenable (UAV's) and was explored in depth in the second year of the grant.

We asked two questions:

* __To what degree do variable nitrogen (N) rates applied to sugarcane correlate with low-cost NDVI measurements?__

* __Are models based on time-series analysis of acquired imagery predictive of sugarcane's yield potential?__

Early in the project we experimented with various capture systems (automatically-triggered cameras) and suspension methods 
using kites and balloons. The central challenge of an aerial system based on wind alone is variability in the 
control of height and nadir positioning of the camera. Wind can also impact the performance of a balloon during flight. 
Additional factors to consider are payload weight and total flight time. 

[Section 3](kites_balloons_drones.md) discussed the various bands of reflected and captured light and how these 
may be used to facilitate an understanding of crop health. In [Section 5]() we will consider in greater detail how 
such principles allow us to manipulate the captured bands and reveal more interesting and specific patterns. 
In this section we will focus on general principles which makes all of this possible. More detailed results from balloon 
and kite methods are presented in [Section 8](study_results_balloons.md). 

#### Creating a Spectral Index 

The steps to create a useful spectral index requires working knowledge of a host of input variables along with 
an understanding of the external environment. Vegetation indices intend only to extract reflected light from 
a crop but in practice many other variables such as soil moisture content, solar angle, camera sensitivity, nadir orientation, 
and others can alter the final index value. The age of a crop itself - i.e. its 'architectural' 
characteristic - may influence and alter an index.

![](img/ndvi_biology.png) 
###### Figure 1. Mechanics of Light Absorption in Plants

Creating an effective spectral index means capturing the right kind of light, at the right time of day,
during the right part of the season, under good weather conditions. In [Section 3](kites_balloons_drones.md) we learned about a set of images that were captured using a pair of consumer cameras. These were later processed to produce both an NRG
image along with a final index image, known as an NDVI index. The mathematical expression used to create an NDVI index 
is as follows:

__(NIR - Red) / (NIR + Red) =  NDVI__

This expression says "subtract the red from the NIR band (in the numerator), add the same red band to the NIR 
(in the denominator), find the quotient between the two." Assume that the amount of visible red light reflected from the tree on the left in __Figure 1__ is 8% and that the amount of NIR 
reflected is 50%. In this case we'd have the following NDVI expression: 

1. (0.5 - 0.08)/(0.5 + 0.08) = 0.42/0.58 = __0.72__ 

An NDVI value of 0.72 (on a scale of 0 to 1.0) indicates that the tree on the left is doing well. It's reflecting 8% of the red light away while absorbing 
the remaining 92% for photosynthesis. It's also reflecting more than half of the harmful NIR light away. 
This is a generic spectral pattern that we can use: _higher NDVI values correlate with healthier, more productive plants_. 
Consider the same equation applied to the tree on the right: 
  
2. (0.4 - 0.3)/(0.4 + 0.3) = 0.1/0.7 = __0.14__ 

Compared with the healthy tree, this one is doing poorly. It's absorbing more than half of the NIR 
light while reflecting away a good portion of the red. Recall that plants use red light to power photosynthesis while NIR 
light presents a physiological burden to them. This is another generic spectral pattern that we can use: _lower NDVI values correlate with unhealthy, distressed plants_. 

#### Interpreting Spectral Indices 

Interpreting a spectral index starts with acquiring accurate aerial image data. Doing so requires consideration of two fundamental issues: 

1. Placing the camera at the correct height and orientation for a sufficient period of time.

    * In [Section 3](kites_balloons_drones.md) three possible methods for positioning a camera 
    in the air (a kite, a helium-filled balloon, and an aerial drone) were considered. Each has its advantages and 
    disadvantages.
    
2. Acquiring sufficient spectral detail from a camera such that the data may be usefully analyzed.

    * The phrase 'sufficient spectral detail' will be unpacked but essentially means clear separation of the 
    individual bands of captured light.
 

__Figure 2__ illustrates a typical NDVI result using a kite-suspension system with two consumer-grade cameras modified 
for NDVI. The image in the center of the figure represents a color LUT (i.e. a look-up table) which is a table of 
numbers used to apply a color transform to an image. Applying this transform allows us to visualize reflected light that 
otherwise would be impossible to see. In this image the LUT is prominently displayed in order to indicate that a full 
range of values has been captured by this image - from dry, sandy soils on the upper left (with an NDVI value of -1) to very active 
areas of photosynthetic activity on the upper right. Also visible are regions of immature crop which are less 
developed on the lower left when compared with the right. 
 
![](img/kite_image_fastie_lut.png)
###### Figure 2. Low cost NDVI

An index image like this is a useful tool for identifying potential trouble spots in a developing crop. Later 
on in the season a flight like this might quickly point out regions of the field that are underdeveloped or damaged. 
While these results are certainly useful and can be achieved for a few hundred dollars and perhaps a 
weekend of practice, they are largely __qualitative__ and __not quantitative__. If the goal was to determine more precisely 
a general pattern over time then this method would present challenges. While not impossible, it is difficult to replicate 
the exact height and vantage point of a image taken during a flight with a kite or a balloon. On another day under different 
conditions these images would be hard to precisely duplicate. Since one of our stated goals was to accurately determine crop 
trends over time using low cost methods we decided to look at other methods.  
 
![](img/pidgeon_camera.png)
#### Resolving Images


Whether one uses a kite, a balloon, a drone, or a pidgeon, once the images have been taken and the craft returned safely to ground,
all images must be gathered and 'stitched' together to create a final representation of the area of interest. 

__Figure 3__ shows the result of stitching a dozen or so images from a balloon flight. This task is commonly 
performed by software but here an application provided by the citizen science group 
[Public Lab](https://publiclab.org/) is used to visually stitch each image over a map of the areal extent. 
This approach reveals how an image is often stretched and distorted in order to make it fit orthogonally onto a planar map. Achieving a 
seamless result requires exact overlap with identical exposure times between images. 

The ultimate goal of stitching images is to form a reflectance map - a mosaic of the area of interest where 
each pixel in the image represents the reflectance of the imaged area. This process is generally known as photogrammetry.

The resolution of the image data gathered and stitched together ultimately rests on a range of factors, each 
representing a point in the overall process where error may be introduced.    


![](img/map-stitch.gif)
###### Figure 3.

In turn, the resolution of the final image __analyzed__ depends on the stability of the capture event, on the resolution 
of the camera at that given moment, and on the stitching process that brings the separate images together. Of interest is the __resolution per pixel__ since each pixel ultimately represents an 
area of the total crop section. With regard to aerial photography, resolution (also called ground sample distance) 
refers to the area of ground covered by an individual pixel. With regard to a digital camera, resolution may also refer to the 
number of pixels in the sensor.  Hereinafter, when using the term 'resolution' we usually mean the ground sample distance. 
We cover this in greater detail in [Section 8](study_results_balloons.md) when discussing the results of kites and balloons.   

#### Vegetation Index With a Single or Dual-Camera System

It is possible to create a vegetation index image using only a single consumer digital camera as almost all consumer camera sensors are
sensitive in the near infrared range. If the camera is modified to remove the IR blocking filter and a dual band pass filter is 
substituted (such that one channel captures visible light and either of the other two channels captures NIR light) this leaves either 
the green or the blue channel available for capturing NIR. However, in this scenario choosing which of the blue or the green channel 
to use has a direct impact on the final result. Furthermore, neither channel is likely to generate a result that 
is comparable to another image taken on a different day under different lighting conditions.  

An improved solution is to use a dual-camera system where one camera captures red light while another captures the NIR. 
In such systems special band pass filters are used to narrow the red and NIR bands captured so that there is less contamination 
between the two. 
 
As an example of a dual-camera system, the composite image in __Figure 6__ represents an RGB/NIR pair in the top row (left/right) 
captured with a pair of consumer digital cameras. The NIR photo on the top-right was taken using a modified Canon A590, 
from which the internal IR block filter has been removed.  

![](img/fastie-results.png)
###### Figure 4.

In the bottom row are two images after post-processing the top two. On the left is a false color IR image (also known as 
an NRG image) with varying tones of red representing the near infrared band. In the bottom-right is a 'normalized 
difference vegetation index' __NDVI__ image which has been created using the pair above. In [Section 8](study_results_balloons.md) and 
[Section 9](study_results_drones.md) we will take a closer look at results obtained when
using these and similar methods. 

#### Consumer-grade versus Professional Systems

* The Spectral Sensitivity of Cameras

![](img/canon_s100.png)
###### Figure 5. A modified Canon S100 consumer camera.

For agricultural purposes, the broadband sensors contained in a modified camera such as the Canon s100 in __Figure 1__ are 
suited to qualitative 'big picture' views of a crop's current status. However, the information provided by such cameras
is limited and does not permit detailed analysis of a crop over time.

![](img/kite_mount.png)
###### Figure 6. Dual-camera system with harness and Picavet (now available from [The Kaptery](http://kaptery.com/)). 

As discussed in [Section 3](kites_balloons_drones.md) a kite or a helium-filled balloon may serve a useful purpose in 
providing a quick overview of a crop but the results produced are often variable and may be difficult to reproduce. 

![](img/solo_camera_mount.png)
###### Figure 7. Sequoia camera (bottom left) with power supply (right) and Sun sensor (top) attached to the 3DR Solo. 

After an initial year of ups and downs using the systems originally proposed it became apparent that 
for a small investment one could use an aerial drone instead. We were among the first 'beta-testers' to fly
a 3DR Solo drone with a Sequoia camera.  

Center wavelength and bandwidth specs for the Sequoia camera are: 


| Band Name | Center Wavelength (nm) | Bandwidth (nm) |
|-----------|:----------------------:|:--------------:|
| Green     |           550          |       40       |
| Red       |           660          |       40       |
| Red Edge  |           735          |       10       |
| Near IR   |           790          |       40       |


#### Qualitative versus Quantitative Science.

Qualitative Research is primarily exploratory research. It is used to gain an understanding of underlying reasons, opinions, and motivations. It provides insights into the problem or helps to develop ideas or hypotheses for potential quantitative research. Qualitative Research is also used to uncover trends in thought and opinions, and dive deeper into the problem. Qualitative data collection methods vary using unstructured or semi-structured techniques. Some common methods include focus groups (group discussions), individual interviews, and participation/observations. The sample size is typically small, and respondents are selected to fulfil a given quota.

Quantitative Research is used to quantify the problem by way of generating numerical data or data that can be transformed into usable statistics. It is used to quantify attitudes, opinions, behaviors, and other defined variables – and generalize results from a larger sample population. Quantitative Research uses measurable data to formulate facts and uncover patterns in research. Quantitative data collection methods are much more structured than Qualitative data collection methods. Quantitative data collection methods include various forms of surveys – online surveys, paper surveys, mobile surveys and kiosk surveys, face-to-face interviews, telephone interviews, longitudinal studies, website interceptors, online polls, and systematic observations.
#### Summary

It became apparent during our study that the ability to place a camera in a relatively steady position for sufficient 
periods of time was a determining factor in whether or not our data would be meaningful for more than a qualitative assessment
at a single point in time. Likewise it became clear that the ability to capture in the narrow band, with minimum distortion, 
was critical. 

Various flying methods, while interesting in themselves, are only a means to the end of placing a camera into 
position in order to capture the right light at the right time of day. Before venturing into the core methods used 
in our study and the results obtained we first set the stage by discussing some earlier methods that were used and why 
they did not succeed. 

###### References
###### __Figure 1__ Image source: https://earthobservatory.nasa.gov/Features/MeasuringVegetation/measuring_vegetation_2.php
######  Jackson, R., and A. Huete. "Interpreting Vegetation Indices." Preventive Veterinary Medicine 11 (1991): 185-200.
###### Ray, T. "A FAQ on Vegetation in Remote Sensing." http://www.yale.edu/ceo/Documentation/rsvegfaq.html, updated 13 October 1994. Accessed February 2014.
###### Steven, M., et al. "Intercalibration of Vegetation Indices from Different Sensor Systems." Remote Sensing of Environment 88 (2003): 412-422.
![](img/farmera.png) 