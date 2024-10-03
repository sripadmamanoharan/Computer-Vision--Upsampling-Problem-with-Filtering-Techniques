# Computer-Vision--Upsampling-Problem-with-Filtering-Techniques

• Performing upsampling on an image and applying Gaussian smoothing with a kernel size k = 11 and scaling parameter σ = 1.
• Evaluating whether Gaussian smoothing improves the result after upsampling.
• Implementing a custom median filter and applying it on the upsampled data.
• ComparingtheeffectivenessofGaussiansmoothingandmedianfilteringtodeterminewhichmethod gives better results.
Analysis Upsampling
Upsampling refers to the process of increasing the image resolution by inserting additional pixels between existing ones. In this task, empty (zero) pixels are inserted between each adjacent pixel, doubling the image size in both dimensions. While this restores the image size, it doesn’t add meaningful information to the inserted pixels. The result is typically a pixelated or blocky image, as the added pixels lack the context from neighboring values.
Gaussian Smoothing
• After upsampling, Gaussian smoothing is applied with a kernel size of k = 11 and σ = 1. This is done to reduce the pixelation artifacts introduced by upsampling.
• The Gaussian filter smooths the image by averaging neighboring pixel values, producing a smoother transition between pixels and reducing sharp discontinuities.
• The kernel size k = 11 ensures that a relatively large neighborhood of pixels is considered for smoothing, reducing pixelation, while σ = 1 controls the spread of the smoothing effect.
Median Filtering
• A custom median filter is implemented to process the upsampled image. Median filtering works by replacing each pixel value with the median value of its surrounding neighbors in a defined window (e.g., k = 11).
• Median filtering is particularly effective for preserving edges and fine details, as it avoids the blurring effect that Gaussian smoothing can produce. It is also more effective at removing impulse noise, such as salt-and-pepper noise.
Implemented both smoothing techniques from scratch without using any pre-defined functions. The smoothing process was applied after the upsampling step to reduce the noise introduced by the interpolation during upsampling.
0.1 Gaussian Smoothing
– A Gaussian kernel was generated based on the provided parameters (kernel size and sigma). – The kernel was then convolved with the image using manual convolution logic.
4
0.2 Median Smoothing
– For each pixel, we computed the median value in a 11 × 11 window around the pixel. – This median value was then assigned to the pixel.
The results are compared.
Results and Observations
Gaussian smoothing produced a visually smoother result. The pixelation from the upsampling process was significantly reduced, and the image appeared more continuous. However, there was a slight blurring of edges due to the averaging process inherent in Gaussian smoothing. While effective in reducing noise, this method might soften important details such as sharp edges.
Median smoothing also effectively removed noise, especially fine noise such as salt-and-pepper artifacts. One key advantage of this method was its ability to preserve edges better than Gaussian smoothing. The image maintained more distinct boundaries between different regions. However, the smoothing in homogeneous areas was not as effective as Gaussian smoothing, as the median filter focuses on noise removal rather than overall smoothness.
Comparison of Results
 Criterion Noise Reduction Edge Preservation Smoothing
ccc
Gaussian Smoothing
Effective in reducing overall noise Blurs edges slightly
Smooths homogeneous regions effectively
Median Smoothing
Very effective in removing salt-and-pepper noise Preserves edges better
Less smooth in homogeneous regions
    Table 1: Comparison of Gaussian and Median Smoothing
Both images (Gaussian-smoothed and median-smoothed) were displayed side by side for compari- son.
– Gaussian Smoothing: The overall image was smoother, but edges were slightly blurred.
– Median Smoothing: The image was sharper, with better edge retention, but did not
smooth out all homogeneous regions as effectively as the Gaussian filter.
Conclusion
Both Gaussian and Median smoothing techniques effectively reduced noise in the upsampled image. However, their effects differed:
– Gaussian Smoothing provides better overall smoothness but may blur important details like edges.
– Median Smoothing is better suited for edge preservation and removing specific types of noise, like salt-and-pepper noise, but does not smooth homogeneous areas as effectively.
Depending on the application, one filter may be preferred over the other. For general noise reduction with less emphasis on edge retention, Gaussian Smoothing is the better choice. For applications where edge preservation is crucial, such as in medical or satellite images, Median Smoothing is more suitable.
