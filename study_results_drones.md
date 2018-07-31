### 9 - Results Using Drones

#### Material and Methods

* An area of second-year sugar cane 'stubble' measuring 1000 ft by 180 ft was dedicated during the 2017 year.
* A series of random sections were laid out and treated with variable amounts of N fertilizer. 
* An aerial drone (described in [Section 4](study_methods.md)) was flown to capture the image data.  

Once planted, a stand of sugar cane may be harvested up to four times in as many seasons. A season runs about 9 months 
and after each harvest the cane remaining in the ground sends up new shoots. While successive harvests give decreasing 
yields, the crop used in this study (a second-year 'stubble') is an ideal 'nitrogen-absorber' and was thus well-suited. 

For the 2017 season, a single-factor field trial was laid out in a common randomized split-plot design on 19 April 2017. 
	
![](img/study_area.png)
###### Figure 1. Ellendale study area measuring 1000 by 120 ft, 2.7 acres total. 

Five levels of nitrogen fertilization (0, 40, 80, 120 and 180 kg·N·ac−1) were applied in a setup with six replicates. 
This resulted in 30 plots of size 100 × 60 sq ft each making a total trial size of 2.75 acres. 

![](img/SARE_GRID.png)
###### Figure 2. Treatment schedule applied during the 2017 sugarcane season.

Sugarcane growth was monitored at 6, 21, 36, 100, 147, and 208 days following N treatment. At 216 days the experimental 
plots were harvested and analysis of sucrose yields was provided. [See Section xxx for details]. The yield was measured following manual harvesting and 
weighing by means of load cells.

Drone flights were made over the study area during the 2017 growth season on eleven separate occasions. Data from half of 
these was used in the analysis. The study area was flown and captured over two separate flights for each date (due to power consumption 
reasons) where each flight overlapped in the center of the field. Calibration of the Sequoia camera was performed between each flight. 

A primary advantage of the drone compared with other methods is the ability to pre-program an exact height (250ft) and range 
prior to each flight. This advantage is clearly demonstrated in __Figure 2__ of the area taken from  'nadir' perspective. It shows 
two 100ft x 60 ft sections in perspective. Here the precision offered by semi-autonomous, programmable drones easily 
outshines other aerial methods considered.  

![](img/RGB_SARE-Cropped.png)
###### Figure 3. A 'nadir' view indicating the relative scale of individual sections.

#### Processing Steps

* After pre-processing steps, each flight yielded a single composite image.
* The composite image was segmented by an automated process into the thirty individual sections.  
* Statistical analyses was performed on each section in terms of four spectral indices.

To capture the study area each drone flight yielded roughly 1200-1500 geotiff images using the [Sequoia camera]() representing 
four narrow bands of light (plus RGB). The raw single band images were layered to produce from 300-350 composite images 
which were then stitched into a single master geotiff containing all four bands (minus RGB). The process of stitching 
geo-coded images is known as mosaicking (see [Section VI](pre_processing_steps.md) ). Mosaiking allows accurate placement of 
acquired image data and projection of those data onto a map. The process is facilitated in this study by embedded latitude and 
longitude tags in each image captured by the Sequoia camera. This allows us to create images of relatively high definition 
containing a broader field of view. 

![](img/NGR_highlight.png)
###### Figure 4. A detail of two treatment sections as a CIR composite image.   

The image in __Figure 3__ has been rendered as an CIR composite for practical reasons. While  since the original raw geotiff from which it was produced is not easily visualized

As mentioned, the composite image contains geotags which form part of the image's metadata. One of the challenges of 
precision mapping is to correctly match a partial image - which may have been distorted in the process of capture - with an 
actual landmark on the ground. Often this process is facilitated through use of ground control points (GCPs). A GCP is an 
invariant point of reference on the ground that stitching software uses to match up points in an image. For our purposes this
process was aided by using a camera that accurately records latitude and longitude points in each image such that they are 
accurately matched in the final composite. A single GCP was used throughout the study, physically placed into the ground 
and referenced from a known surveyor's benchmark. The GCP is located in the right-most part of the following image near 
the intersection of two white lines.     

![](img/NGR_SARE-Cropped.png)
###### Figure 5. A CIR composite showing section detail and the grid used to apply different nitrogen amounts. Color differences indicate different treatments.   

__Figure 5__ shows results of a flight which occurred on July 28, 2017. This image has been rendered as an CIR composite 
for practical reasons since the original raw geotiff from which it was produced is not easily visualized. The image clearly 
shows, as red light, the conditional coloring of luminosities in the near infrared band. Also visible are differences in 
the areas that have been treated with variable amounts of nitrogen.

Our treatment schedule for 2017 was __0__ lbs N per acre, __40__ lbs, __80__ lbs, __120__ lbs, and __180__ lbs per acre.
These amounts were chosen as they reflect a sensible range around the recommended treatment for this particular species 
(120 lbs per acre).

#### Comparing Plots

* Individual treatments (per section) were analyzed across early, mid-season and late-season growth using automated methods.

The development and growth of the leafy part of the sugar cane plant plays an important part in helping to maximize the 
interception of solar energy for photosynthesis. This leads to the accumulation of biomass and ultimately to a higher crop 
yield [1]. Canopy closure in sugar cane represents that point in the growth season where the adjoining tops of two rows come
together and obscure from above the cane stalks below.   

-------
![](img/2017-04-25_001_3_CIR.png)
![](img/2017-04-25_001_3_NDVI.png)
![](img/2017-04-25_001_3_GNDVI.png)
###### Figure 6. CIR composite image, NDVI versus GNDVI index in an early sugar cane crop. 

In __Figure 6__ three images are displayed: a CIR composite of a single section (taken on April 25, 2017) followed by two index images
processed from the same section for NDVI and GNDVI. The color bars to the right represent index values on a scale 
of 0 to 1. The mean 'soil-corrected' index value for each section was __0.46__ for NDVI and __0.4__ for GNDVI. These values 
were generated for all sections, for all treatments, and used in the final regression analysis. Our
approach was to average a cumulative 'index signal' for each section and compare this with the final sucrose yield 
for that section following harvest. 
 
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

![](img/2017-07-28_021_3_CIR.png)
![](img/2017-07-28_021_3_NDVI.png)
![](img/2017-07-28_021_3_GNDVI.png)
###### Figure 7. CIR composite image, NDVI versus GNDVI index in mid-season sugarcane growth. 

In __Figure 7__ a CIR composite, NDVI and GNDVI from a section taken on July 28, 2017 are shown. The mean 'soil-corrected' 
index value for these was __0.83__ for NDVI and __0.73__ for GNDVI. Given the obvious visual difference of these two images,
that the values are basically equivalent (after accounting for the scale difference) is of interest. 

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.


#### Regression Analysis

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

![](img/ndvi/ndvi_winner.png)
![](img/N_bar.png)

###### Figure 8. foo bar foo bar foo bar foo bar foo bar foo bar foo bar foo bar foo bar 

The graph in Figure [x] above shows NDVI values during the first month of the growing season, from late April, 2017 
(one week following application of N fertilizer) to late May.

#### Multiple Regression

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

![](img/ndvi/ndvi_one2three.png)
![](img/ndvi/ndvi_four2six.png)
![](img/N_bar.png)

###### Figure 9.

#### Animated Results

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

![](img/animated/animated-ndvi.gif)
###### Figure 10.

#### Faceted Regression Results

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

_corrected ndvi_
![](img/ndvic/ndvic_all_spectral_data_mark.png)
_ndre_
![](img/ndre/ndre_all_spectral_data_mark.png)
_gndvi_
![](img/gndvi/gndvi_all_spectral_data_mark.png)
_ndvi_
![](img/ndvi/ndvi_all_spectral_data_mark.png)
![](img/N_bar.png)

###### Figure 11. Regression 'facets' showing index values versus yield (April to November 2017).


#### Temporal Evolution of Vegetation Index in Sugarcane

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

![](img/ndvic/ndvic_correlation.png)
###### Figure 12. Correlation of NDVI-C Index with Yield (lbs sugar per section).

__Figure 12__ shows the temporal evolution of a 'soil-corrected' spectral index during the 2017 growing season.  

![](img/ndre/ndre_correlation.png)
###### Figure 13. Correlation of NDRE Index with Yield (lbs sugar per section).

__Figure 13__ shows the temporal evolution of the NDRE spectral index during the 2017 growing season.  

![](img/gndvi/gndvi_correlation.png)
###### Figure 14. Correlation of GNDVI Index with Yield (lbs sugar per section).

__Figure 14__ shows the temporal evolution of the GNDVI spectral index during the 2017 growing season.  

![](img/ndvi/ndvi_correlation.png)
###### Figure 16. Correlation of NDVI Index with Yield (lbs sugar per section).

__Figure 15__ shows the temporal evolution of the NDVI spectral index during the 2017 growing season.  

#### Summary

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.


###### References

[TBD]

![](img/farmera.png) 
