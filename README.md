# Computational Astrophotography using Image Processing

**Arnav Jalan**  
**Arnav Aditya**  
**Aditya Raghuram**  
**Jaideep Singh**  
Computer Science and Engineering  
Shiv Nadar University  

Email: 
- aj713@snu.edu.in
- aa716@snu.edu.in
- ar694@snu.edu.in
- js452@snu.edu.in

---

## Abstract

This paper presents an exploration into the realm of low-cost astrophotography through the application of image processing techniques. Traditional astrophotography has been characterized by high costs and technical barriers, limiting access to amateur astronomers. However, recent advancements in image processing algorithms have enabled the enhancement and extraction of valuable information from raw astronomical images obtained with consumer-grade equipment. This paper delves into the potential of computational astrophotography in improving image quality and increasing the resolution of the celestial horizon. Through a series of equations and mathematical methods, the efficacy of various image processing algorithms, including image thresholding, Otsu’s method, bilateral filtering, and more, is demonstrated.

## 1. Introduction

Astrophotography, the practice of capturing images of celestial objects using DSLR cameras, has gained widespread popularity among enthusiasts and professionals alike. However, the pursuit of this hobby often comes with significant financial barriers, particularly stemming from the need to counteract the Earth’s rotation during long exposure times. As celestial objects traverse the sky during these exposures, star streaks—bright lines tracing their trajectories—can mar the quality of the images. While some photographers intentionally incorporate these streaks for artistic effect, they pose a challenge for those seeking precise representations of the night sky.

To address this issue, astrophotographers commonly rely on moving camera and telescope mounts to compensate for the Earth’s rotation. However, the cost of these specialized mounts can be prohibitive, placing the practice of astrophotography out of reach for many aspiring enthusiasts. This paper proposes an alternative approach: leveraging computational techniques to mitigate the effects of Earth’s rotation during long-exposure imaging. By harnessing the power of digital image processing, we aim to eliminate the need for expensive rotating mounts, thereby making astrophotography more accessible and affordable.

## 2. Related Work

Current astrophotography practices often involve physically moving the camera to compensate for Earth’s rotation. However, efforts have been made to alleviate the necessity for such physical adjustments. Notably, a technique has been proposed that remaps star streaks to polar coordinates, ensuring a consistent point-spread function for all stars in the image. Additionally, Richardson-Lucy deblurring techniques have been employed to address quality degradation in star images. Furthermore, maximally sparse optimization approaches have been explored to enhance image fidelity by minimizing noise and artifacts. These endeavors collectively underscore the ongoing exploration of computational methods to enhance the accuracy and clarity of astrophotographic imagery.

## 3. Data Collection

Data collection methods involve capturing raw astronomical images under varying conditions to test the efficacy of different image processing techniques.

## 4. Image Segmentation

To turn the lines of stars into points, we use image segmentation to isolate the star streaks. The process involves several steps:

### 1. Thresholding

We carry out three distinct thresholding methods to isolate star streaks from the rest of the image:
- **Global Thresholding**: Captures the brightest star streaks.
- **Otsu’s Method**: Distinguishes the background from the foreground while segmenting a different group of star streaks.
- **HSV Thresholding**: Detects fainter streaks by converting the image to HSV representation.

### 2. Width Estimation

We incorporate neighboring pixels within a certain gradient from the pixels eliminated by the thresholding methods to account for varying streak widths.

### 3. Combining Methods

After executing the three thresholding methods, we merge the results to maximize the number of streaks removed while ensuring minimal information loss.

## 5. Star Streak Modification

### 1. Finding the Polar PSF (Point Spread Function)

Star streaks are transformed into polar coordinates with the origin at the celestial pole to convert them into approximately horizontal lines.

### 2. Star Clustering

A recursive algorithm clusters bright pixels and averages their values to compress them into single pixels.

### 3. Star Replacement

The blurred image is combined with the modified star image to replace the streaks with accurately colored point stars, preserving background continuity.

## 6. Image Post Processing

### 1. Hole Filling

Empty regions where stars were located are filled with the average value of surrounding pixels to maintain visual continuity.

### 2. Smoothing and Noise Filtering

A bilateral filter is employed to refine the image and reduce residual noise.

## 7. Results and Discussion

Qualitative analysis of the generated images exhibits visually pleasing attributes, while quantitative assessments indicate successful streak removal and efficient processing times.

## 8. Conclusion

We successfully developed an algorithm to mitigate star streaks, replacing them with accurately-colored point stars. Future work includes exploring alternative segmentation methods and improving gap-filling strategies.

## Acknowledgments

The authors would like to express their gratitude to Professor Saurabh Janardan Shigwan for his invaluable guidance, and to Teaching Assistant Tanvir Singh for his assistance and feedback.

## 9. References

1. B. D. Jeffs and M. Gunsay. Restoration of blurred star field images by maximally sparse optimization. *IEEE Transactions on Image Processing*, 2(2):202–211, April 1993.
2. L. W. H. W. Y. H. Laili Su, Xiaopeng Shao. Richardson-Lucy deblurring for the star scene under a thinning motion path. 9501, 2015.
3. N. Otsu. A threshold selection method from gray-level histograms. *IEEE Transactions on Systems, Man, and Cybernetics*, 9(1):62–66, Jan 1979.
4. B. Sease and B. Flewelling. Polar and spherical image transformations for star localization and RSO discrimination. 01 2015.

