# Brain Tumor Segmentation

### Preprocessing!- Skull Stripping

Skull stripping is a process of the brain tissue segmentation (cortex and cerebellum)
from the surrounding region (skull and non brain area). It is also a very important
preprocessing step which precedes further analysis in case of many MRI
neurological images (such as image registration or tissue classification). In clinical
practice, this method is widely used in developing automated methods for progress
evaluation of neurodegenerative diseases such as: Alzheimer’s disease, multiple
sclerosis and other neurological disorders like brain aging or even some mental
illness.

Skull stripping techniques can be divided into 3 main categories:

  - Intensity-Based methods. They are based on the threshold classification. The
  main disadvantage of this approach is its significant sensitivity for intensity
  fluctuations (in case of MRI caused for example by magnetic field in
  homogeneity, registered noise or even device’s properties)

  - Morphology-based Methods. The basic idea is to combine the use of
  morphological operations, thresholding and edge detection techniques, in
  order to separate the area of the brain from the surrounding tissue in the most
  precise way.

  - Deformable Model-based Methods which applied the active contour
  deformation and fitting to localize brain area and its identification by using
  image characteristic.

### Project structure
```bash

├── README.md
│ ├── outputfiles // contains pgm and jpg mri scans
│ │ ├── pgm
│ │ └── jpg
│ ├── Skullstipped // contains skullstripped output images
│ │ └── stripped_image_i.jpg
├── SkullStripping.ipynb
├── t1_icbm_normal_1mm_pn3_rf20.rawb //rawb data volume 

```
### Installation

Install the dependencies and devDependencies and start the server.

```sh
Fork the repository
$ git clone https://github.com/sraycju/BrainTumorSegmentation.git 
$ cd BrainTumorSegmentation

```
### About Dataset

Dataset link : https://brainweb.bic.mni.mcgill.ca/selection_normal.html

raw byte (unsigned) : One (unsigned) byte is used for each voxel, and the
data is scaled such that it will use the entire 0...255 range of values.

Exception: the "crisp" anatomical models are not scaled -- their byte
values will be in the range 0...10.
For example, the displayed header info:
![image](https://user-images.githubusercontent.com/81697577/209388716-8d916d8d-4911-4ea1-a438-b7ea63ea858d.png)


should be interpreted as follows:
  - The file scans the 3D image volume such that the 'X' coordinate
  changes fastest, and the 'Z' changes slowest.
  - The image sizes along the X-Y-Z axes are 181x217x181 voxels
  (pixels).
  - The voxel sizes along the X-Y-Z axes are 1x1x5 mm.
  - Using this header info, you should be able to correctly read the raw
  volumes on any kind of computer platform.

### Flow


RAWb to pgm conversion -> PGM to JPG -> Designing a Mask for the Brain Extraction -> Skull Stripping using opencv -> Skull Stripped images


### Results

#### Initial Raw MRIs

![slice_0](https://user-images.githubusercontent.com/81697577/209389387-5934ecb0-bc12-4623-bbe4-2122890ee1f6.jpg)
![slice_84](https://user-images.githubusercontent.com/81697577/209389393-dd3151de-1f7e-4af4-b6ff-2e2de97ca700.jpg)
![slice_90](https://user-images.githubusercontent.com/81697577/209389399-86063d52-c788-479e-861d-4eb2054e4f0d.jpg)
![slice_100](https://user-images.githubusercontent.com/81697577/209389402-151b835e-f312-4294-9809-4b7999f9dec9.jpg)


#### Skull Stripped Images

![stripped_image_87](https://user-images.githubusercontent.com/81697577/209389686-7ecd4313-c9d9-44a7-9555-fdb4ebbbfc7e.jpg)
![stripped_image_88](https://user-images.githubusercontent.com/81697577/209389697-2bf32424-31ba-4cd9-9371-701f5d8e7be5.jpg)
![stripped_image_89](https://user-images.githubusercontent.com/81697577/209389702-5cf7c930-20b4-4633-8d2c-4b8054022cf1.jpg)
![stripped_image_90](https://user-images.githubusercontent.com/81697577/209389707-c646f42e-448d-4946-aa9a-24a44736c48d.jpg)



