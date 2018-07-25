### Kites, Balloons, and Drones

#### Aerial Photography
* Aerial photography is a primary data source for precision agriculture.
* The goal in aerial data capture is to produce consistent, stable images.
* Cameras in flight are inherently unstable.

The history of taking photos from high-flying objects is a long and storied one involving blimps, balloons, 
parachutes and kites, pigeons and personal drones. All have been set aloft with ingenious cameras 
attached and tools to trigger them either remotely or automatically. The French caricaturist Gaspard-Félix Tournachon (known as 'Nadar') 
was first to fly and photograph the city of Paris from above in 1858.

![](img/nadar.png)
###### Figure 1. Gaspard-Félix Tournachon hangs on, making history. 

Whichever airborne method is used the object remains to position one or more cameras at sufficient height, point 
them down (or as close to nadir as possible), get the shot, and return the camera safely to the ground. No method 
discussed here performs in every way without producing some kind of error. 

#### Kites
* Kites are easy to understand.
* In certain conditions kites are incredibly stable and will fly for extended periods.
* Kites can play a role in agricultural photography but only to a point. 

In the image below (courtesy of Ron Marcisak) a camera is suspended from a kite using a device 
known as a Picavet. The Picavet (named for French inventor Pierre Picavet) attaches the camera to the 
line that flies the kite. The Picavet consists of a rigid cross 
suspended below the kite line from two points and serves to stabilize the camera against random motion.

![](img/kite.png)
###### Figure 2. A camera system suspended via Picavet from a Delta-style kite. 

Kites represent an easy and accessible approach to suspending cameras in the air. A kite has the advantage that,
given a strong and stable wind, it's easy to fly and will remain suspended for long periods. 
On the other hand, while a Picavet is good at orienting the angle of the camera roughly downward, it 
can't prevent the camera from being jostled about during flight. The result is often many blurried images mixed with 
a few good captures having the right orientation.       


#### Balloons

* A helium-filled balloon provides an accessible solution for suspending cameras.
* Balloons can serve as an alternative to kites on wind-less days.
* Helium is an expensive, non-renewable resource. 

The image below is of a 2 meter wide polyethelene balloon filled with helium gas. It employs a Picavet system similar to 
the one seen on the kite. It also suspends a dual-camera system. The main difference is in how a balloon flies which is 
straight up unless a wind is pushing it elsewhere. Helium balloons are sensitive to wind and may be guided off 
course quite easily by it. On wind-less days they rise easily to great altitudes and can remain steadily in place for 
several hours.    
 
![](img/balloons.png)
###### Figure 3. A helium-filled balloon suspends a dual-camera system. 

Balloons and kites are a practical tools where high-resolution imagery is required. When using balloons, weather conditions 
are important to consider since winds may impact the flight plan. The caveat of never putting into the air anything you 
aren't prepared to lose is especially relevant with a helium-filled balloon. If you lose control it will continue to ascend 
and drift possibly into areas where it doesn't belong (i.e. into an airport's flight path). 

A more practical issue regarding helium-filled balloons is that the element itself is in short supply. In some areas of the 
world use of helium is restricted to essential medical and research purposes only. A world-wide shortage of helium 
has led to a sharp rise in cost for this light-than-air gas. One should rightly consider this when deciding on helium 
use for non-critical purposes. Helium is naturally released from fossil fuel production sites and may be captured 
and stored. However, after use it's not easily re-captured but ultimately escapes into space forever. 


#### Unmanned Aerial Vehicles (i.e. Drones)

* Aerial drones (UAVs) are unique among the other methods discussed.
* UAVs provide stability and reproducibility over individual flights.

A recent development in aerial photography addresses some of the weaknesses found in other methods. While a UAV is 
technically an aircraft without a human pilot in fact all aerial drones rely on human direction. Perhaps 
it's more accurate to say that drones act semi-autonomously while being piloted remotely. Either way, they represent a 
significant improvement over other methods discussed in agriculture.

Several key attributes make UAVs unique among the other methods. Chief among these is the ability to receive a pre-programmed 
flight plan where the height and extent of every flight is reproducible from one flight to the next. As we will see in 
later sections, this capability is especially important in the context of agriculture. 

Aerial drone prices have dropped in recent years but owning and operating one remains an substantial 
expense. While a number of turnkey services provide all-in-one flight and data services, as in any new endeavor, 
understanding the steps involved and the actual value-add is crucial for success.  


![](img/drone.png)
###### Figure 4. A 3DR Solo drone in mid-flight. The Solo was used in this study. 

Here are some ways that aerial drone technology is being applied in agriculture:

* __Soil and Field Analysis__ 
    * UAVs can be used at the start of a crop cycle to produce 3D maps. After planting, 
    soil and field analysis maps can help direct irrigation and nitrogen-application.
*  __Planting__ 
    * Planting systems directed by UAVs can achieve higher uptake rates and lower overall planting costs.
* __Crop Spraying__ 
    * With ranging technologies such as LiDAR drones can be used to apply the correct amount of liquid fertilizer 
    or pesticide to the ground for even coverage. 
* __Crop Monitoring__ 
    * How to scale an effective crop monitoring plan remains an issue for most farmers. 
    Satellite imagery has been used for large-scale crop monitoring but these data can be imprecise and
    are often expensive. Time-series data from successive UAV flights can show the development of a crop much more effectively. 
* __Health Assessment__ 
    * With UAVs it is possible to scan a crop in the visible and near-infrared bands
    and identify which areas are healthy or unhealthy. Vegetation indices can be used to track changes 
    in crop health over time. 
    
While the goals of our study necessarily limits discussion to the last two categories (i.e. monitoring and 
assessment of the health of a crop) these and other efforts like them have created a kind of revolution in agricultural
practice. When we began our study the autonomous drone was not an option unless one had very deep pockets and a 
background in aviation. Two years ago their use was limited and largely theoretical. Since then UAVs have quickly evolved 
and become firmly established as a new norm in agriculture.   
 
#### A Segue into Light, Cameras, Action

Our discussion into various flying methods, while interesting in itself, is only a means to an end of placing a camera into 
position in order to capture the right light at the right time of day. Before venturing into the core methods used 
in our study and the results obtained we first set the stage by discussing some earlier methods that were used and why 
they did not succeed.  

#### Resolving Images
Whether one uses a kite, a balloon, a drone, or a pidgeon, once the images have been taken and the craft returned safely to ground,
all images must be gathered and 'stitched' together to create a final representation of the area of interest. 

__Figure 5__ shows the result of stitching a half-dozen images from a balloon flight. This task is commonly 
performed by software but here an application provided by the citizen science group 
[Public Lab](https://publiclab.org/) is used to visually stitch each image over a map of the areal extent. 
This approach reveals how an image is often stretched and distorted in order to make it fit orthogonally onto a planar map. Achieving a 
seamless result requires exact overlap with identical exposure times between images. 

The ultimate goal of stitching images together is to form a reflectance map - a mosaic of the area of interest where 
each pixel in the image represents the reflectance of the imaged area. This process is generally known as photogrammetry.

The resolution of the image data gathered and stitched together ultimately rests on a range of factors, each 
representing a point in the overall process where error may be introduced.    


![](img/map-stitch.gif)
###### Figure 5.

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
###### Figure 6.

In the bottom row are two images after post-processing the top 
two. On the left is a false color IR image (also known as an NRG image) with varying tones of red representing the near 
infrared band. In the bottom-right is a 'normalized difference vegetation index' __NDVI__ image which 
has been created using the pair above. In [Section 8](study_results_balloons.md) and 
[Section 9](study_results_drones.md) we will take a closer look at results obtained when
using these and similar methods. 

[Bottom line is kites, balloons, single or dual camera systems are good for some things not good 
for others.]

#### Summary
Of all aerial methods discussed thus far UAVs prove to be the most capable in that they allow...
Small and large growers alike may benefit from the steep reduction in price and complexity of these wondrous devices. 
Using these tools growers can farm more economically and acquire the most valuable forms of data as need and suited to their
specific needs.  

###### References
* History of Aerial Photography Professional Aerial Photographers Association (retrieved 5 October 2016)
* https://en.wikipedia.org/wiki/Nadar
* Ron Marcisak https://www.flickr.com/photos/ronskap/13173764143/in/pool-kaprigs/
* Alan McConchie https://www.flickr.com/photos/almccon/
* Sam Pepple, Sample Cartography (stiched map image)
* Chris Fastie, Courtesy of the [Public Lab](https://publiclab.org/).

![](img/sugar_button.png) 
