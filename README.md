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
    
    
