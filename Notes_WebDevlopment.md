
************************************************
				General Web Design
************************************************

***********************************************************
Things to Remember
***********************************************************

WEB BROWSER ENGINe
***********************************************************

Webkit  -   Safari
Blink   -   Edge, Chrome, Opera, its a fork from webkit
Gecko   -   Firefox.
Servo   -   Mozila Experimental browsers.

WEB BROWSER COMPONENTS
***********************************************************

UI Front End    -
UI Back End     -
Data Storage    -
Network Component   -
JS Engine           -
Rendering Engine    -
Browser Engine      -

WEB BROWSERS WORK
***********************************************************

HTML Parser - > DOM Tree (DOM)
CSS Parser  - > CSS Tree (CSSOM)

                        -> Render Tree
                                        -> Layout
                                                    -> Painting

For Any Script Execution the Parser Stops till the JS execution is completed.
Any JS Execution stops still the Depended CSS is not parsed.

All this CSS, HTML and JS parsing and execution happens in the Main Thread.

Event Loop manages the execution of all this using a message queue. It’s an infinite loop that pulls tasks such as layout, painting, and JS execution from a message queue and processes them.

WEB DESIGN
***********************************************************

1. Typography

    1. Body Text Should be between 15px to 22px.
    2. Use Big Fonts for Headlines.
    3. In case of Big Fonts , reduce the Font Weight.
    4. Use line Spacing between 120% to 150%.
    5. 45 to 90 Chars per line is ideal.

2. Good Fonts

    San Serif   -   Lato, Raleway       , Used for Modern Websites
    Serif       -   Cardo, PT Serif     , Used for Traditional Websites, Storytelling 

3. Color

    1. Use only one base color.
    2. gray and white are not counted as the base color.
    3. Use Color to draw attention.
    4. Never use black for Design.

4. Images

    1. Image Overlays can be used to show text over and image. 
    2. Put Text in a box with background to make text stanout. The box should have some transparency.
    3. You can use blured image and put the text in blured area.
    4. You can also use an out of focus image area.
    5. Image with a floor fade, that means darker at the bottom.

5. Icons

    1. Can be used to show features or steps.
    2. For actions and links.
    3. Icon should be labeled if space permits.
    4. Icon should have genral meaning.
    5. Icon should not take center stage.
    6. Use Icon fonts instead of static images.
    7. Raster Images dont scale, while Vector images can scale infinitely.

6. Whitespace and Spacing

    1. use whitespace between element, group of elements, between sections etc.
    2. White space creates hirarchy.

7. How to Learn

    1. Collect designs that you like
    2. Try to understand everything about it.
    3. What these sites have common.
    4. Use developer team and inspect.
    5. Steal like an artist.