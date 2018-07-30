### 5 - Varieties of Spectral Index

#### What's A Vegetation Index?

* A multi-spectral index is an expression relating bands of light as they reflect from an object.
* Narrow bands of light energy reflect from plants and inanimate objects in distinct ways.

There are a [hundred different ways](https://www.indexdatabase.de/db/i.php) to create a spectral index, all sharing the 
property of representing a *ratio* where bands of light are manipulated in the numerator or denominator of a simple mathematical 
expression. Generating and interpreting a vegetation index (a spectral index applied to vegetation) provides 
a reliable way to compare a plant's photosynthetic activity and structural variation over time and space. A 
common spectral index used in agriculture for gauging the health of plants is 
[NDVI](https://en.wikipedia.org/wiki/Normalized_difference_vegetation_index) ('Normalized Difference Vegetation Index'.) 

 
#### Calculating a Vegetation Index

Calculating a VI requires converting an image or set of images into a set of  *rasters* - rectangular grids of pixels or 
points of color. Each pixel contains a set of values corresponding to the captured bands of light. In familiar RGB 
terms each pixel contains a Red, a Green and a Blue score. Such scores reflect the power, or luminosity, of electromagnetic 
radiation for that particular band as it comes into contact with the sensors of a digital camera. Most of the indices 
used in this study make use of an inverse relationship between red and near infra-red reflectance values commonly associated 
with healthy green vegetation. 

![](img/rasterbands.gif)
###### Figure 1. Raster arrays representing different bands of light.  

An example vegetation index is NDVI which is calculated from an image in the following way: 
1. Subtract the NIR band reflectance values in all pixels from all the Red values. 
2. Add all NIR values in each pixel to all the Red values.
3. Calculate the ratio between the calculated difference (the numerator) and the calculated sum (the denominator). 

Calculating NDVI requires first creating and manipulating two separate images (pixel arrays) each of which contains light 
from a separate wavelength. The NIR band is contained in one layer while the red is held in another. Manipulating each pixel, 
of each layer, according to a mathematical expression, produces a third raster layer which is the NDVI image itself. 
All of this is accomplished using software designed to perform matrix arithmetic over large arrays.  
    
An NDVI index is a ratio of the difference and the sum of two narrow bands of light. A ratio is taken in order to 
*normalize* the values with the effect that this binds them between -1 and 1. Plant NDVI values can range from 0 to 1 but 
usually lie somewhere between 0.2 and 0.8. NDVI and other index variability values are 'dimensionless' meaning 
the physical values from which they derive cancel one another. Some common vegetation index values explored during our study
include:

1. __NDVI__ = (NIR - RED) / (NIR + RED)
    * The workhorse of vegetation indices. NDVI reveals the physical basis of most other VI's i.e. the relationship 
    between absorbed/reflected amounts of red and NIR light. In our study, NDVI was best at revealing biomass differences. 
    We found it to be most effective in the early to mid-growth part of the season. It tended to lose some sensitivity 
    following canopy closure. 

2. __SAVI__ = (NIR - RED) /  (NIR + RED + L) * (1 * L)
    * The soil-adjusted vegetation index (SAVI) is a modification of NDVI intended to correct for soil brightness. 
In areas where soil is exposed, reflectance of light is altered in the red and NIR bands and this can 
influence the result. The issue may be present during the early part of the growth season. We addressed 
this sort of issue by use of a masking technique discussed in [Section 9](readme_resources/study_results_drones.md). 
    
3. __OSAVI__ = (NIR - RED) /  (NIR + RED + 0.16)

    *   OSAVI is derived from the Soil Adjusted Vegetation Index (SAVI) above. It's sensitive to canopy density but not
    soil brightness. Where vegetation cover is > 50% it can help dampen the saturation effect that NDVI is prone to.
    We used this index in the latter part of the 2017 season with mixed results. 

4. __NDRE__ = (NIR - RE) / (NIR + RE)
    * NDRE is available only in cameras that are sensitive to the 'Red Edge' band of spectral light. It's a better 
    general indicator of plant health for mid to late season growth when compared to NDVI. NDRE is also thought to be 
    capable of mapping variability in foliar Nitrogen levels, which we were interested in. Green and red-edge bands 
    penetrate the leafy part of the plant more so than the blue or red bands. Thus red-edge is more sensitive to 
    chlorophyll content and to nitrogen contained in the leaf. We used this index extensively. 

5. __GNDVI__ = (NIR - Green) / (NIR + Green)
    * As indicated by the name, the Green Normalized Difference Vegetation Index is related to NDVI (or RNDVI) in that 
    it uses the green band where NDVI uses the red. GNDVI is an index of 'greenness' and by that measure it is more 
    sensitive to photosynthetic activity, specifically to the variation of chlorophyll content in plants.
    
6. __CIR Composite__ (Color Infrared) 
    * Unlike other values described a CIR Composite is not an index. Instead of displaying the common RGB bands it combines 
    the NIR, Red, and Green bands such that the NIR is shown as red, the red as green, and the green 
    as blue. This allows the NIR light to be visualized as red.

#### Choosing an Index Value for Sugarcane

When light interacts with a crop it is partly reflected and partly absorbed. The spectral response of sugarcane plants 
varies according to their state (see Figure 1). At visible wavelenghts of the spectrum, corresponding to Green and Red 
light, the reflectance of the canopy is lower than the bare soil; at Near Infrared wavelenghts the vegetation and the 
bare soil have different reflectances but are similar at Middle Infrared wavelengths. The Middle Infrared wavelength
band is important for separating trash from others states of the crop


![](img/choose_index_1.png)
![](img/choose_index_2.png)
###### Figure x

#### Summary
Remote sensing techniques provide timely, up-to-date and relatively accurate information for the management of sugarcane crop.
Thus far we've discussed simple calculations applied to single image pixels. In practice, generating a vegetative index
over an crop involves much more. In addition to separate individual bands as arrays we 
need to scale these sorts of manipulations up to potentially __millions and millions__ of pixels covering __hundreds 
and hundreds__ of megabytes of image data.

In coming sections we'll discuss how to achieve this degree of scaling along with strategies for interpreting 
various vegetation indices under different environmental conditions. Luckily, open-source software and image processing 
tools exist to make these tasks accessible.

###### References

[TBD]

![](img/farmera.png) 