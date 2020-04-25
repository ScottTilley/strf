Instructions:

- The 'w' and 'W' keys are all you need to control all of the functionality.Â  'w' selects a point and 'W' resets only the screen size so you can zoom into the data to see individual bins and reset as needed to relocate as you reduce the trace.Â  The two keys like this make for fast work flow...Â  More on that below.

- First select with 'w' one point immediately above OR below the wideband data you would like to reduce a point from, a '+' will appear at that location on the screen.Â  This selection will anchor the time so it is the one you need to be accurately aligned with over or under the data.Â  Next, go to the other end of the swath of data and hit 'w' again, another '+' will appear.Â  The alg will run and place a 'o' where it figures the centre of the curve is and save the point.Â  Now you are ready to repeat on a new wideband swath.

![PLOT1](https://github.com/ScottTilley/strf/blob/master/plot1.png)

- If you've zoomed in too much and need to relocate on the curve to reduce more points hit 'W'. This will reset the screen so you can zoom in on different areas of the curve and allow you to accurately select more points.Â  Using 'W' only affects the screen zooming and will not delete your marks and points from the screen.Â  This is so you can proceed with a reference of what you have done and what you need to complete.Â  I find the zoom level in the first image below about right for accurate placement of the first point.Â  The second point can be anywhere along the x-axis as long as it's in the spot on the y-axis you want.Â  I find it helpful to give a little margin at either end of the data selection of no signal data.Â 

![PLOT2](https://github.com/ScottTilley/strf/blob/master/plot2.png)

Here's the result of reducing an entire curve in the image below.

![Image description](https://github.com/ScottTilley/strf/blob/master/plot3.png)

- To delete your marks from the screen use 'r' as usual.

- As you mark your points they are reduced to a file called wide.dat.

A few notes on how the alg works:

   The slice of the spectrum between the points selected is taken and the data has it's log taken.
   The data is then fit to ax^2+bx+c to fit a parabola and the coefficients a,b and c are obtained.
   From the coefficients obtained, the vertex of a parabola is solved using the equation vertex_x = -b/2a, thus in theory identifying the peak of the data blob.
   The value is converted to MJD and Frequency and the point logged to wide.dat.
   There is a certain amount of filtering in the alg. to prevent invalid entry of x,y mouse coordinates to prevent program crashes.Â  Otherwise the code seems robust.
   One area of improvement could be to implement a Weighted Gaussian solver as they are more immune to noise and could improve the reduction of data overall particularly with noisy data.



