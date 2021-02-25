# Styling lineart in Hackaday colors

Black diagrams on white backgrounds is jarring to the eye when embedded in Hackaday's dark themed articles. This can be [greatly improved](https://hackadaycom.files.wordpress.com/2018/06/renesas-df2117vbg20v-block-diagram.png) by altering images to have a dark background, white text, and yellow lineart.

Here is the workflow Mike uses in Gimp to go from black and white to Hackaday theme:

1. Get the best quality source image you can
1. Colors-->Color to Alpha to make the white background transparent
1. Duplicate the layer.
1. Manually select text and delete it from one of the layers
1. On the layer from which you just removed text, use the "Select by color" tool to select the transparent background.
1. Select-->Invert to select the lineart that is left over
1. Now switch to the other layer and press delete. This will remove everything that is not text from this layer (this becomes our white text layer)
1. Switch back to the other layer; Colors-->Colorify (on Gimp 2.10 this menu item is missing, type `/colorify` and press enter to open the dialog)
1. Click on "Custom color:" and enter #F3BF10
1. Set the foreground color to #1A1A1A, make a new layer using that foreground color and send it to the bottom of the layer list
1. Export the image. (If exporting as a jpg file, make sure to deselect "Save color profile" as it causes a bug in Wordpress Jetpack that changes the background colors if that data is present)

## Protips

* When using color to alpha, what remains may not be a solid color. Sometimes duplicating and merging the layer will help make the layer bolder
* Brighter whites: If the white looks more grey you can try using Colors-->Levels and sliding the output levels slider on the left all the way over to the right.
* If there is a lot of compression noise or other non-white in the image it may be better to use the Select by Color Tool to select the background, changing the threshold as necessary.
  * Once most of the background is selected, you can use the Select-->Grow tool to included a pixel of two of anti-aliasing before using the color to alpha tool.
  * After running color to alpha, Select-->Shrink a few pixels then hit delete to remove the background noise
* If there are other colors in a graphic, I sometimes use the Select by Color Tool to put those in their own layers.
  * Change these colors to suit the dark theme using either the Color-->Hue-Saturation tool or Colors-->Map-->Color Exchange (although this doesn't work well with anti-aliasing)
  