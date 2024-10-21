## Image Analysis and Visualization

<a target="_blank" href="https://colab.research.google.com/drive/1V9FQeQEfb01tjHj4JAgF_fe9JNxVRb7g?usp=sharing">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

This code performs **image analysis and visualization** to compare pixel-level statistics between two sets of facial images: one representing **young adults** and another representing **older adults**. The analysis focuses on calculating and visualizing the **mean pixel values** and **standard deviations** for each set of images, allowing a side-by-side comparison between the two age groups.

### Steps Performed

1. **Loading or Generating Image Data**:
   - The images of both young and older adults are loaded or pre-processed.
   - These images are represented as 3D arrays of shape **256x256x3**, where:
     - `256x256` refers to the dimensions of the image.
     - `3` refers to the color channels (likely in LAB or RGB format).

2. **Calculating Pixel Means**:
   - For each set of images (young adults and older adults), the code computes the **mean pixel value** at each pixel position across all images in that group.
   - This results in an "average" image for each group, where each pixel represents the average color intensity across all images in that group.
   
   The mean is calculated using the formula:
   <img width="162" alt="Screenshot 2024-10-21 at 11 04 30 PM" src="https://github.com/user-attachments/assets/489ae465-d5f5-4560-bc40-d5e7936dbf9a">

   Where:
- μ is the mean pixel value.
- X_i is the pixel value at position i.
- N is the total number of pixels.

3. **Calculating Pixel Deviations (Standard Deviation)**:
   - The code calculates the **variance** for each pixel, which represents how much the pixel values deviate from the mean. The **standard deviation** is then computed as the square root of the variance.
   
   The variance for each pixel is calculated as:
  <img width="223" alt="Screenshot 2024-10-21 at 11 05 52 PM" src="https://github.com/user-attachments/assets/ae9def21-020b-4731-9a17-762cc220717e">

   The **standard deviation** (σ) is then:
   <img width="104" alt="Screenshot 2024-10-21 at 11 06 36 PM" src="https://github.com/user-attachments/assets/724ac608-b39a-42be-b96a-940241fd8447">

   - The standard deviation is computed for each pixel across all 3 color channels.
   - The deviations are then **summed across the color channels** to produce an overall deviation value for each pixel.
   - The deviation values are **normalized** using the Euclidean norm:
     
  <img width="181" alt="Screenshot 2024-10-21 at 11 07 05 PM" src="https://github.com/user-attachments/assets/99986451-53c9-4b29-8559-783d025c5181">

   This normalization scales the deviations for comparison across the two groups.

4. **Visualizing the Results**:
   - The code generates visual representations of the pixel means and deviations:
     - **Pixel Means**: Displays the average pixel values for both young and older adults, resulting in a "mean" face for each group.
     - **Pixel Deviations**: Visualizes the variability (standard deviation) of pixel values, using a reversed colormap to highlight differences between the two age groups.
   - The visualizations are shown side-by-side for easy comparison.
  
![Unknown-4](https://github.com/user-attachments/assets/53767c0d-7417-4d21-9c94-741c23b9271b)
![Unknown-5](https://github.com/user-attachments/assets/d0cda07e-ce9c-4aa6-ad78-2ab044b447b9)


