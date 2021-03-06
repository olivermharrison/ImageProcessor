# ImageProcessor

A C++ project that explores image processing algorithms on PNG images.

## Installation

This project is compiled using g++ and make. To install, clone this repository and run `make` in the project root folder.
This will generate an executable in the `/bin` directory.

## Execution Example

`./ImageProcessor <image.png> <flags>`

## Flags

The available image processing options are given below. <br/>
Flags may be stacked, for example  `./ImageProcessor image.png -i -k 3 -s` will invert, quantize and sharpen the image in that order.

Flag | Arguments | Description | Example Output
---- | ---- | ----------- | --------------
-i | | **Invert** image by finding 255-RGB for each pixel. | ![Alt text](examples/invert.png?raw=true "Invert")
-g | | **Greyscale** conversion by averaging RGB values. | ![Alt text](examples/greyscale.png?raw=true "Greyscale")
-t | t[0, 255] | **Threshold** pixels by setting RGB values <= t = 0 and values > t = 255. | ![Alt text](examples/threshold.png?raw=true "Threshold")
-k | k[1, 255] | **Quantize** colours by running K-Means with k centroids. | ![Alt text](examples/quantize.png?raw=true "Quantize")
-b | | **Blur** image by convolving with a Gaussian kernel. | ![Alt text](examples/blur.png?raw=true "Blur")
-s | | **Sharpen** image by convolving with a kernel that emphasizes differences in adjacent pixel values. | ![Alt text](examples/sharpen.png?raw=true "Sharen")
-e | | **Detect edges** by converting to greyscale and convolving with an edge detection kernel. | ![Alt text](examples/edges.png?raw=true "Edges")


## Tests

This project uses [Catch](https://github.com/philsquared/Catch) for unit testing which can be conducted by running `make test` in the project root folder. <br/>
Please note that if you're on Windows you'll need to uncomment `#include <Windows.h>` in `tests/src/config.cpp`.

## License

Please see [Catch](https://github.com/philsquared/Catch) and [LodePNG](https://github.com/lvandeve/lodepng) for their respective licenses.
Any other code may be used in any way you wish.
