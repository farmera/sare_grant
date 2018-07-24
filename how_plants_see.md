#### Through the Eyes of a Plant

###### Basic Plant Biology

* Plants use chlorophyll, water, and carbon dioxide to synthesize sugar.
* Sugars make roots, leaves, flowers, seeds.
* Chloroplasts are cells containing chlorophyll. Chlorophyll absorbs light mainly in red and blue wavelengths.
* Green light is absorbed less and is reflected away (thus plants are green).

While our study's purpose is to provide a 'proof of concept' regarding use of aerial tools to determine the health 
and productivity of sugar cane, before discussing whether a certain approach is valid,  we should first understand 
the basics of what such systems actually measure and how they achieve this. As most learn in middle school, 
photosynthesis is a process that plants use to synthesize sugar from carbon dioxide and water. 

The leaves of 
plants contain photosynthetic engines known as chloroplasts. When the sun's rays hit these chloroplasts, which are 
mainly contained in the leafy portions of the plant, cells absorb the red and blue wavelengths while reflecting away 
most others. This filtered light, along with water and carbon dioxide, produces sugar and oxygen.

###### Red, Blue and Near Infra Red (NIR)

* Healthy plants absorb red but reflect away most of the NIR.
* NIR is higher energy light, most plants cannot use it.
* A healthy plant has a distinct 'spectral signature' based on these reflectance properties.

Visible light is that part of the continuous electromagnetic spectrum which lies roughly between 380 and 750 
nanometers (nm). The more healthy a plant is - i.e. the more photosynthesis it carries out - the more red light 
it tends to absorb. This tendency is directly related to the functional health of choloroplast cells since these are the 
locus of the photosynthetic process. If a plant's chloroplasts are compromised then it will absorb less red light
and its ability to photosynthesize and produce sugar will likewise be diminished.  

![](/Users/geraldmc/2018Code/sare/sare_grant/readme_resources/img/one.png) 

__Figure 1.__

   
In addition to absorbing red (and blue) and reflecting green, most (healthy) plants tend to reflect away almost all of 
the NIR light that hits them. This tendency is shown in the graph above. NIR light is not in the visible spectrum 
and thus we cannot see it. Neither may plants convert NIR light to useful energy. It is in part to avoid the 
damage that NIR otherwise causes that plants reflect most of it away. 

In the above graph, reflectance values are on the 'y' (vertical) axis while the wavelength of light is on the 'x' 
(horizontal) axis. In healthy plants blue light is largely absorbed and only a little is reflected. As we move further 
into the green we see that the amount of reflectance increases. In the red it is again diminished while in the NIR 
(the grey region) almost all is reflected away. 

In addition to showing the generic 'spectral signature' of plants this graph also indicates the difference 
between plants that are healthy and those that are not, in terms of spectral signature. The blue line indicates 
health while red demonstrates unhealth. Note that an unhealthy plant absorbs less in the blue 
and red parts of the spectrum while absorbing more (reflecting less) in the NIR portion.   
 

###### Modified RGB Cameras
* Spectral bands collected by RGB cameras overlap. 
* Spectral overlap leads to contaminated values.
* Modified RGB cameras are difficult to calibrate.

So how does one 'see' the sorts of spectral signatures that crops exhibit? An obvious start (discussed [here](readme_resources/kites_balloons_drones.md)
at length) is to get the right sort of camera high into the air and take a lot of pictures.
In a market that's rapidly evolving knowing how to choose the right camera at reasonable cost can be a challenge.

In a sense all cameras are multi-spectral insofar as they capture more than a single band of light. The typical consumer
camera is multi-spectral, sensing light in the red, green and blue parts of the spectrum. Consumer cameras as a rule do 
not capture light outside of the familiar RGB range. Or do they? In fact any standard Canon Powershot (the kind you can 
find on Ebay for $100) in fact __does__ capture NIR light but this capacity has been concealed by the manufacturer (to 
reinstate it just remove a filter). Suffice it to say that mass production of digital sensors provides them with a very 
high degree of often unrealized sophistication.
 
While consumer cameras can be 'hacked' such that they absorb both visible and NIR light, a problem in doing this is 
demonstrated by the following graphic:

![](/Users/geraldmc/2018Code/sare/sare_grant/readme_resources/img/two.png)

__Figure 2.__

The above highlights the spectral characteristic of a generic consumer camera. The first thing to recognize is the 
degree of overlap between the color bands. Consumer cameras are not designed to separate these bands which is perfectly 
fine in the context of taking pictures of kittens. When the intended goal is to provide separation between bands 
(for purposes of quantifying values) it's not helpful. 

###### Professional Multi-Spectral Cameras

* Multispectral cameras are tuned to capture multiple, narrow bands of light.
* The 'spectral signature' of a plant helps indicate its productivity.

An alternative to consumer-grade RGB cameras is a more expensive 
camera designed from the ground up to function as a truly narrow-band multi-spectral instrument. 

![](/Users/geraldmc/2018Code/sare/sare_grant/readme_resources/img/three.png)

__Figure 3.__

Specialized multispectral cameras contain 'band-pass' filters which whittle down the wavelengths of light to more 
narrow bands. Having access to these narrower bands provides a far more precise estimate of the luminosity of 
light reflecting off of plants.    

In sections to come we go into greater detail about specific low and high end multi-spectral cameras including examples 
of each in action. We'll also discuss how to scale and manage large volumes of image data in this sort of workflow.  Finally, 
we'll consider along with strategies for interpreting various vegetation indices under differing environmental conditions. 
Luckily, open-source software and image processing 
tools exist to make these tasks more accessible to the average user.


###### References
 