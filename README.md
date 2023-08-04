# How to...
## ...refine a QGIS color ramp
QGIS uses preset color ramps for cartographic presentation. Most are familiar with the basic Symbology settings, but the preset color ramps often do not represent the spatial arrangement in the most clear way because the color breaks are preset and not necessarily to our needs. 

**Here is what I learned while trying to achieve the right look for my map of Sao Miguel island of the Azores archipelago rendered from a hillshade elevation raster.**

Color ramps have preset pallettes with preset breaks, and depending on the type of classification of the color/value pairs, they can be vastly inappropriate to display the meaning we want to convey through the map. This is less of an issue with choropleth maps where the values classification is flat (covers a polygon with a single color), but this type of color ramp is definitely not suited for elevation maps, for example. 

For these applications, the Symbology setting should be at "Singleband pseudocolor" , the Band is going to be the value reflecting the hillshade, "Band 1 (Gray)" in this instance, and the "Interpolation" is set to "Linear" to capture and accurately represent the elevation data stored in the hillshade raster. Once the basic parameters are set, we can click "Classify" to break the color ramp to cover the elevation data.

![image](https://github.com/agidak/Blog2/assets/93615593/effa6a1c-35df-45dd-9e5c-063448c3ba65)

However, we are still stuck with the generic color ramp. We can find nicer color ramps sets by clicking on the color bar itself and choosing the type of color ramp we need from the small pop-up:

![image](https://github.com/agidak/Blog2/assets/93615593/f2d900f2-50e1-4fbe-bcbf-895986d77a8b)

This will open a window that contains special preset color palettes that are crafted for specific scenarios. The "cpt-city" group of color palettes has many thematic arrangements, and we can find preset color ramps created for different types of terrain within the "Topography" menu option:

![image](https://github.com/agidak/Blog2/assets/93615593/b13e28f2-b1a4-467b-a7de-5a71a9d7a3dc)

However, even here, the color palettes can be hit or miss depending on the context. For my map of Sao Miguel, the "elevation" palette looks pretty garish, and the color shifts look abrupt, so I would have to change this for a nicer articulation of the terrain.

![image](https://github.com/agidak/Blog2/assets/93615593/8d7af6b2-7943-4647-9020-5763d4c2ae58)

I can look for another palette that suits my sensibilities and the context better, like cpt_city's "c3t1":

![image](https://github.com/agidak/Blog2/assets/93615593/9b9c6c3e-c2c3-47df-a39b-c2e067630316)

This has a nice pastelly look about it and smoother color shifts. The only problem is that it does not have an appropriate range for high elevations. While the hues are nice, this color ramp is too flat:   
![image](https://github.com/agidak/Blog2/assets/93615593/790bd4b3-df42-4f1b-a2a4-c10204314ba6)

But QGIS does not have a very direct way to adjust the color ramp. One way I was shown to resolve this problem is by adjusting the color of every color tile in the classification window--a very arduous task...

## *Here is the trick:*
We can adjust the color palette once we check the option "Save as standard gradient" in the palette window and clicking OK:

![image](https://github.com/agidak/Blog2/assets/93615593/0fc876b7-01e6-447e-8cfc-a33ed371788c)

Now, we can click onto the color ramp in the Symbology window, which will open a new window for editing the color ramp:

![image](https://github.com/agidak/Blog2/assets/93615593/f12bf11b-8355-4cb4-a1d9-36496b1a6733)

This window allows us to
- add new gradient stops
- adjust the range of the colors on the color palette so as to skew the range differently
- change the colors associated with the gradient stops, so by the end, the color ramp looks quite different.

From here:  ![image](https://github.com/agidak/Blog2/assets/93615593/984e54a2-50bc-46c1-adc8-e44825f777be)

To here:   ![image](https://github.com/agidak/Blog2/assets/93615593/e0315008-d22f-4051-ac63-2ae0feb3ac40)

Once we are done with the adjustments and OK it, the new color palette will show up in the Symbology color ramp display, and once we OK that, it will show up on the map layer display as well:

![image](https://github.com/agidak/Blog2/assets/93615593/b4b19a31-3e57-43bf-9e73-0f763a7b67a6)

With some more tweaking of the colors, I ended up with the following elevation layer for my map. It suits the island's elevation much better because the color gradient reflects the steep hill sides on the small island. It also worked much better in the ultimate context of the map image, a tourism brochure with images of nature.

![image](https://github.com/agidak/Blog2/assets/93615593/a1949f16-fb66-4903-a118-758c4330a325)

It is a quick trick that opens the opportunity for endless fiddling with the color ramp that could be eventually saved among our favorites for future projects.
*Color away...*








