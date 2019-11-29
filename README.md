# Pyramid Blending


## Synopsis

In this project, I'm putting together a pyramid blending pipeline that will allow you to combine separate images into a seamlessly blended image. The technique is based on the paper [“A multiresolution spline with application to image mosaics”](http://persci.mit.edu/pub_pdfs/spline83.pdf) (Burt and Adelson; ACM 1983) (see lessons Module 04-03 Pyramids, 04-04 Image Blends).

![Pyramid Blending](blend.png)

## Directions

- Images in the `images/source/sample` directory are provided for testing. 

- You can execute the blending pipeline by running `python main.py`. The script will look inside each subfolder under `images/source`, looking for folders that have images with filenames that end with 'white', 'black' and 'mask'. For each such folder it finds, it will apply the blending procedure to them, and save the output to a folder with the same name as the input in `images/output/`. (For example, `images/source/sample` will produce output in `images/output/sample`.)

- The blending procedure splits the input images into their blue, green, and red channels and blends each channel separately. You do not have to worry about dealing with three channels; you can assume your functions take in grayscale images.

- Along with the output blended image, main.py will create visualizations of the Gaussian and Laplacian pyramids for the blend. You may use or refer to these to explain your code in your report, but they are not required. 


### 1. Implement the functions in the `blending.py` file.

  - `reduce_layer`: Blur and subsample an input image
  - `expand_layer`: Upsample and blur an input image
  - `gaussPyramid`: Construct a gaussian pyramid from the image by repeatedly reducing the input
  - `laplPyramid`: Construct a laplacian pyramid by taking the difference between gaussian layers
  - `blend`: Combine two laplacian pyramids through a weighted sum
  - `collapse`: Flatten a blended pyramid into a final image

The docstrings of each function contains detailed instructions. You may only have a limited number of submissions for each project, so you are *strongly* encouraged to write your own unit tests. The `test_blending.py` file is provided to get you started. Your code will be evaluated on input and output type (e.g., uint8, float, etc.), array shape, and values. (Be careful regarding arithmetic overflow!)


### 2. Generate your own blended images

I took "white" and a "black" images which are used for combination. Then created a custom "mask" image that defines the regions to combine. Run images through the pipeline.
