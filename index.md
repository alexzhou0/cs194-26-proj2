## CS 194-26 Project 2: Fun with Filters and Frequencies!

### Part 1: Fun with Filters
#### Part 1.1: Finite Difference Operator
![Cameraman Image](website_images/cameraman.png)

To compute the gradients of the image, we convolve the image with the finite difference operator in the X and Y directions shown below to get the gradients in those respective directions (G_x, G_y). We can compute the magnitude by just taking the squareroot-sum-of-squares of these two results. 

![Finite Difference Operators](website_images/filters.jpg)

The result can be seen below:

![Gradients after Filtering](website_images/cameraman_grad.png)

After binarizing the photo, we can see that we get more defined lines, although the result is really noisy. I chose a threshold of 80 for this.

![Gradients after Thresholding](website_images/cameraman_thresh.png)

#### Part 1.2: Derivative of Gaussian (DoG) Filter
If we first blur the image with a Gaussian filter, then perform the gradient computation, we can get much smoother edges. This can be seen below. We can also combine the Gaussian filter with the gradient filters by convolving the filters together, then convolving with the image to save computational cost. The result ends up being the same, as expected.

![Gradients after Gaussian Filtering](website_images/cameraman_dog.png)

#### Part 1.3: Image Straightening

![Facade Straightening](website_images/facade.png)

![Eiffel Straightening](website_images/eiffel.png)

![Lecture Straightening](website_images/lecture.png)

![Pisa Straightening](website_images/pisa.png)

As we can see in the last photo, the "straightening" of the Tower of Pisa doesn't work, since the tower is supposed to be tilted, but is significant enough in the photo compared to the horizontal things on the ground that the output image is "straightened" such that the tower is no longer leaning as much. A middle ground is chosen, since my straightening algorithm allows some tolerance around -180, -90, 0, 90, and 180 degrees.
