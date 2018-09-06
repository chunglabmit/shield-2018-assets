# shield-2018-assets
Binary assets for shield-2018 docker image

This repository contains binary file assets that are useful when running
the software in the shield-2018 Docker image. They are included here using
GIT LFS so that they can be downloaded by the shield-2018 script to
work-around lack of GIT LFS support in docker hub.

The binary files in the "atlas" directory are derived from files generated
by the Allen Brain Atlas group. If used, they should be cited as
"Allen Mouse Brain Atlas (2018)" (see https://alleninstitute.org/legal/citation-policy/)

The files in the "atlas" directory:

* **AllBrainRegions.csv** - a CSV file that can be used with the Nuggt
**count-points-in-region** command to map segment IDs to region names.
* **annotation_25_half_sagittal.tif** - the reference segmentation
of the right half of the mouse brain. Each voxel is labeled with either
"0" if it is outside of the brain or a label from **AllBrainRegions.csv**.
* **autofluorescence_25_half_sagittal.tif** - a 3D image of the autofluorescence
intensity of the right half of the mouse brain, aligned with the
annotation image. See http://help.brain-map.org/download/attachments/2818169/MouseCCF.pdf 
for details of its construction.
* **coords_25_half_sagittal.tif** - coordinates, in X, Y, Z form, for keypoints
for alignment for the **autofluorescence_25_half_sagittal.tif** reference
image. This can be used as an input for **sitk-align** using the --xyz switch.
* **autofluorescence_25_half_sagittal_cropped_cbellum_olf.tif** - a version
of **autofluorescence_25_half_sagittal.tif** that has the cerebellum and
olfactory bulb masked out. This can be used to align a mouse brain where these
structures have been removed or are missing.
* **annotation_25_half_sagittal_cropped_cbellum_olf.tif** - a segmentation
derived from **annotation_25_half_sagittal.tif** where the cerebellum and
olfactory bulb have been masked out.
* **coords_25_half_sagittal_cropped_cbellum_olf.tif** - coordinates, in X, Y, Z form, for keypoints
for alignment for the **autofluorescence_25_half_sagittal_cropped_cbellum_olf.tif** reference
image. This can be used as an input for **sitk-align** using the --xyz switch.
