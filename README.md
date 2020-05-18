# Lab_Report_Creator
This is tool to automate lab report creation using Cmake

## Pre-requisites

1. Git
2. Make
3. CMake

Command to get the pre-requisites in a debian based system (you can easliy find similar command for other distros):

`# apt install git build-essentials cmake`

## Usage

#### Get the repo

Clone the repo using:

`$ git clone --recursive-submodule <repo-url>`

You can find the repo-url by clicking the green button "Clone or Download"

**Note:** We are using the [cmake-pandocology](https://github.com/jeetsukumaran/cmake-pandocology) project as the submodule so you need to use the `--recursive-submodule` flag to get it during cloning.
Thanks to the contributers and owners of cmake-pandocology for building such a useful project.

#### Save your file in src floder as following:-
1. description file as description.md.
1. code file as code.c.
1. input values file as input.txt.  
1. output of code as output.txt.
1. flow chart image in src/img folder with name img.png

Change to build directory:

`$ cd build`

If build folder is already populated then run " rm -r * " in build folder
then run  following commands

`$ cmake ..`

`$ make`

You will get finaloutput.pdf file as your lab report in build/product.
