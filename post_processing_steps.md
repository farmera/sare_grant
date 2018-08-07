### 7 - Post-Processing Spectral Imagery

#### Introduction

This section describes in detail some tools and methods used to generate and interpret 
statistics from multi-spectral indices. These and other post-processing steps have formed a large 
part of our exploration of available methods for understanding the relationship between a given spectral index and 
the final sucrose yield in sugar cane.

While a number of technical details are discussed we hope to present them in a manner that remains
accessible to non-technical users. A primary goal of this study is to provide information and access to methods 
for working farmers, not technical people. Of course there will always be specialized knowledge, one cannot
be expected to know all of it. Still, much of this work is accessible, more so than might first appear.
It's an under-appreciated fact that growers are, as a rule, adept at picking up a new technology as often they must be.

#### Open Source Automation Tools

* A range of open source tools are available to assist in processing multi-spectral imagery. 
* Automation of the processing steps is both possible and desirable using open source models.

Our study made use of a number of software tools and libraries that are freely available as open source
projects. Among other things, 'open-source' means that installing, learning and using these software products is open to 
anyone who has an interest. There are no licensing fees. In the context of this project all tools described have been 
applied during the study and new code continues to be added on a daily basis to our project repository [here](). 
We have drawn on the strength of open-source tools in order to implement many pre- and post-processing steps. In fact, 
even the drone used in the study runs a stripped-down version of the open-source Linux operating system, i.e. one may 
login, get a command prompt, and execute code on the drone. 

#### Post-Processing Steps

In any part of a multi-step process looms the spectre of error. This is especially true if the process relies on 
manual execution of a number of steps. In every phase of this project we have sought to minimize error by __automating__ 
as much of the work as possible. The processing system designed for our project consists of six automated steps. 
The first four are required to prepare the raw image data prior to analysis. The fifth and sixth are post-processing steps 
that are subsequently performed. In this section we consider __masking__ and __extraction of image-derived 
statistics__. 

1. Mosaicking
2. Atmospheric correction
3. Geometric correction
4. Image co-registration
5. __Masking__
6. __Extraction of image-derived statistics.__


#### Practical Examples

* Different spectral indices offer alternate views of the same data. 
* Seasonal variation in spectral data can be addressed through basic machine learning techniques.

We tested a variety of spectral index types during this study, always with the goal of discovering which was best suited 
to the task of revealing an elusive set of values.

One question we sought to answer was how interaction of NIR light with soil effects the spectral index
of an early sugar cane crop. __Figure 1__ shows a pair of early season NDVI images, one taken in late April 
and one from late May. Nitrogen treatments for this crop occurred on April 19, 2017. The two images 
are significant insofar as they reveal the initial response to treatment and the sensitivity of a specific 
index type in capturing it. Each image is an NDVI of the same section over time following application of 80 lbs N per hectare. 
The first was taken 6 days after N application and serves as a baseline. The second is
one month later in the season. 

It turns out that this is a typical sort of task in post-processing spectral data. We want to analyze image pairs in 
order to derive a better sense of the sensitivity of a particular index, and to correlate the average index values of each 
pair. However, at least half of the visible area in these images is composed of __soil__ which should not 
be included in the averaged NDVI value (e.g. soil is _not_ photosynthetic).

Thus the task is to remove pixels from an image where those pixel values represent soil. How might one accomplish this? 
One way is to open up each image in an editor, examine every pixel and guess, based on color, whether it should be 
included in the final average or not. Each of these particular section images contains ~30,000 pixels and there are 30 
sections in each dataset. That's roughly 900,000 pixel decisions to make for each.  

![](img/ndvi_compare_1_with_hist.png)
###### Figure 1. Histogram of uncorrected NDVI values.

Instead of counting pixels, another approach is to look more closely at how the two images stack-up. To do this we 
can plot them as 'dual' histograms, as is done in __Figure 2__. Note that there are multiple peaks in each histogram (one 
is colored yellow and the other purple). The yellow peak at far left is most prominent. This peak indicates that 
'soil' pixels have an average NDVI value between 0.1 and 0.2. There are also peaks found in the purple histogram, 
corresponding to NDVI values from the 05/25 image, though these are not as prominent as the 04/25 image.      

#### Masking

Examining the histogram of 'uncorrected' NDVI values in __Figure 2__ we see that the mean NDVI value for 04/25 and 05/25 is 
0.26 and 0.52, respectively. These averages include the soil pixel values in addition to the plant material. We can 
use the same data that generates the histogram as input into a type of 'classification' machine learning algorithm known
as __minimum threshold__. This algorithm assumes that the image contains two pixel classes (foreground and background) which 
are used to calculate an optimum threshold to separate the two. In plain English this means that by applying the algorithm 
we're automatically masked the more prevalent pixel type (in this case the non-photosynthetic ones) in a manner that is repeatable, 
i.e. it is not solely based on one individual's judgement.        

![](img/ndvi_1_corrected.png)
###### Figure 2. Histogram of 'corrected' NDVI values.

The result of applying minimum threshold is seen in a second set of images and in a histogram generated from the 
'thresholded' data (see __Figure 3__). No longer do we see the prominent peaks (the 'soil' pixels are replaced 
by 'neutral' white). The second set of averages more accurately reflects the actual NDVI values of the 
crop, minus the noise. These values (in the 'corrected' versions for 04/25 and 05/25) are 0.42 and 0.65, respectively.

![](img/uncorrected_ndvi_three.png)
![](img/corrected_ndvi_three.png)
###### Figure 3. Set of soil corrected and uncorrected NDVI images.

This simple use of machine learning illustrates how automating a single step in the chain reduces error overall. __Figure 4__ shows a set of three uncorrected/corrected NDVI images from May 25, 2017. The nitrogen treatments are, from left 
to right, 40 lbs N, 80 lbs N and 120lbs N. In the top row the unbiased standard deviations are 0.17, 0.17, and 0.18, 
respectively, while in the corrected versions they are 0.9 in each. In this case we've managed to remove some of the 'noise' 
from the samples which proves to be of significance when a final interpretation of these data is made.  

#### Extraction of Image-Derived Statistics

* High resolution section images were used to create each vegetation index.
* Statistical Analysis was performed on the vegetation index images.

__Figure 4__ below compares two NDVI images taken early in the growth season, at Day 6 following treatment and 
at Day 21. Section images like these were used as input to the statistical analysis and are the 'last word' on
our reported results. The specific images here are 412 by 72 pixels in size, where each pixel has a ground 
resolution of 2.7 centimeters (~1 square inch). These data were captured at a height of 250 ft while flying the 
drone at a speed of 10 mph. A single image capture occurred each second and comprised a set of RGB, Green, Red, Red Edge, 
and NIR images.     

![](img/04-25_ndvi.png)
![](img/05-25_ndvi.png)
###### Figure 4. Comparison of NDVI images from April 25, 2017 and May 25, 2017. 

The images in __Figure 5__ below demonstrate subtle differences when using an alternative vegetation index at a 
different point in the growth season. Two groups of nine sections are displayed, the top group is NDVI, the bottom group is 
GNDVI. Reading each from left to right advances time from early season to the high point of photosynthetic activity. 
Reading from top to bottom shows an increase in nitrogen treatment from 80 lbs N to 180 lbs N.

![](img/multiples_134_NDVI.png)
--------
![](img/multiples_134_GNDVI.png)

###### Figure 5. General comparison of NDVI versus GNDVI performance in early to mid-season sugarcane.

When analysed statistically these image data reveal that, when compared with NDVI, GNDVI shows a lower correlation with yield data overall but may 
be better suited at certain points in the season. As indicated by the leftmost column, use of the green band in sparsely 
vegetated sections decreases the sensitivity of GNDVI while denser sections (right-most column) tend to benefit by 
dampening the saturation that occurs with NDVI later in the season. Surprisingly, the central column is where GNDVI 
'out-performs' NDVI in terms of its ability to correlate with the final yield values.

#### Quality Control
An issue faced by this study and others like it is the relatively small number of samples produced, along with the 
distortions due to error that any one sample may accrue before reaching the analysis phase. Our 2.7 acre test area 
contained 30 section plots with five treatments each, i.e. six samples for each date flown. Half of the flight data yielded 
inconsistent results and was rejected.   

![](img/compare-one.png)
###### Figure 6. Comparison of different index types in the same section, same treatment. 

For data which we felt were generally acceptable we then imposed an additional set of criteria regarding what an index image needed 
to have in order to be considered 'suitable for framing'. Our criteria included running various statistical analyses on 
different index types taken in the same section and/or treatment. For example, while the images in __Figure 6__ have not 
yet been 'soil corrected' they reveal a characteristic relationship between GNDVI and NDVI where the former has 'less energy' 
i.e. it displays fewer hits per bin across the entire reflectance range and those hits are more 'bunched' together around a mean value.        

![](img/compare-two.png)
###### Figure 7. Comparison of the same index for different sections, similar treatments. 

In a similar way we can compare index images from different sections that use the same index to measure a similar 
treatment. The treatments in __Figure 7__ are for 40 lbs N (yellow) and 80 lbs N (blue). The NDVI values that make up 
this histogram are for sections imaged on the same day (on the same flight) at Day 36 following treatment. What we expect 
to see is a characteristic shift to the right of the plot receiving the higher treatment and indeed this is what 
we do see in the figure.  
 
![](img/compare-three.png)
###### Figure 8. Comparison of the same index for different sections, same treatment. 

The last sort of comparison we did, as a means of 'proofing' whether or not an image sample was acceptable, was to check different
sections with the same treatment. In __Figure 8__ two NDVI images that received 0 lbs N in different parts of the
field have similar (not identical) histogram plots.  

#### Summary

Reading the last part of this section closely might raise the legitimate concern that we have pre-selected data that is 
most likely to submit to a favorable analysis. Perhaps there is some truth to that in that there is a tension 
between cleaning data so as to removes outliers and 'null' values (which is acceptable) and removing meaningful 
information. A guiding principle of this study has been to reveal whether or not certain low-cost methods are amenable to a 
certain amount of rigor. Getting a half dozen consistent datasets was a challenge  for this study and it was thought that 
given what we set out to achieve special care should be paid to knowing whether or not the data were clean prior to analysis.      
  
###### References

[TBD]

![](img/farmera.png) 