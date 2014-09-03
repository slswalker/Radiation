This project adds a Photos extension that allows the user to tile their photo in a Golden Spiral.
The user has the ability to change the orientation of the spiral to any of the four spiral starting locations.

The extension's spiral is generated to start at the original size of the image and spiral downward.

The algorithm behind laying out all of these items works like this:

1. Create tiles sized such that each incremental tile is an addition of the previous two, whether in height or width, and is
determined based on the orientation of the previous two tiles. Do this until the next tile would be larger than our
original image.

2. Scale the largest image to the size of the original image.

3. Iterate from smallest to largest tiles to scale them by the same scale amount used in step 2.

4. Iterate from largest to smallest to position the tiles in a Golden Spiral layout. At first, the only known location
of any tile is the largest based on its orientation. The each incremental one below it is known based off the previous
frame and orientation.

5. Generate an image from the original image by filling in all of the tile frames with the original image and adding
some white space inbetween each photo, because it can get hard to discern the edges of the photos otherwise.

6. Rotate spiral start location when requested by the user and start over at step 1.

This project supports quicklook for the GoldenSpiralImageModel class. It will display the layout of the Golden Spiral
if it has calculated it already from the algorithm above. 


This project prototypes the very popular flickr layout from 2013 (in the case that they have changed).
The algorithm behind laying out all of these items works like this:
    Size page: Iterate through each item and build up a list of items that when resized to the height of 
    the first item in the current row being sized. Stop adding items to the current row when we have
    gone over the width of our view bounds + half the width of the last item.
    Size row: Size the total width to fit equal to our width bounds and then calculate a reducing ratio 
    value for the first item. Use this ratio to calculate the row height after applying it to the first item
    Then use the row height to reduce all subsequent items heights and widths.
    Cache rows: After each row is done we can cache that row and each of the items and so that our collection view
    can ask for each items position and size at any time
    
This prototype also makes use of Core Data and using a main thread concurrency type and a private queue 
concurrency type hierarchy to save changes in the background and propogate them to the main thread
    
    
