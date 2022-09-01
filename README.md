# Self-adaptative-Feature-tracking-with-PCA-Lucas-Kanade
The inability to change size has always been a drawback of sliding window tracking. If the previous frame of the current frame is used as the reference frame, the error rate is often superimposed. 
Therefore, this is still not the best solution.
If only using traditional feature tracking methods such as SIFT, SURF or Lucas-Kanade, it's impossible to track a specific object and there is no defined object frame to define the overall features of the object to be tracked. Using Deep Learning (DL) for object tracking such as Siamese Tracker requires training of the object to be tracked, and the size of the tracking bounding box cannot be defined arbitrarily while tracking. We propose to use Principal Component Analysis (PCA) as the feature extraction mechanism and Lucas-Kanade (LK) tracking optical flow as the object size prediction: 

1. No time-consuming DL training is required for the objects, every object is trackable. 
2. The object frame size can be defined arbitrarily. 
3. Automatically detects and adjusts object size even if it changes.

This repostory is based on my previous repostory [Feature-tracking-with-PCA](https://github.com/JacobChen1998/Feature-tracking-with-PCA).
If you are insterented how to track based on PCA, please check the detail from there.

<!-- ![tracked_result_before_adjust](https://github.com/JacobChen1998/Self-adaptation-Feature-tracking-with-PCA-Lucas-Kanade/blob/main/tracked_result_before_adjust.gif)
![tracked_result_after_adjust](https://github.com/JacobChen1998/Self-adaptation-Feature-tracking-with-PCA-Lucas-Kanade/blob/main/tracked_result_after_adjust.gif)
![optical_flow_LK](https://github.com/JacobChen1998/Self-adaptation-Feature-tracking-with-PCA-Lucas-Kanade/blob/main/LK_result_kangaroo2_ref_firstframe.gif) -->

| ![ssr_comparison.png](https://github.com/JacobChen1998/Self-adaptation-Feature-tracking-with-PCA-Lucas-Kanade/blob/main/tracked_result_before_adjust.gif) ![tracked_result_after_adjust.png](https://github.com/JacobChen1998/Self-adaptation-Feature-tracking-with-PCA-Lucas-Kanade/blob/main/tracked_result_after_adjust.gif) ![optical_flow_LK.png](https://github.com/JacobChen1998/Self-adaptation-Feature-tracking-with-PCA-Lucas-Kanade/blob/main/LK_result_kangaroo2_ref_firstframe.gif) | 
|:--:| 
| *Figure 1: Visualization tracking result. Only tracked with PCA, i.e. [Feature-tracking-with-PCA](https://github.com/JacobChen1998/Feature-tracking-with-PCA),(left). This method (middle). Optical flow that generated by Lucas-Kanade algorithm used to assist tracking in this repostory (right).* |

| ![Algorithm_pipeline.png](https://github.com/JacobChen1998/Self-adaptation-Feature-tracking-with-PCA-Lucas-Kanade/blob/main/Algorithm_pipeline.png) | 
|:--:| 
| *Figure 2: * Pipeline of our feature tracking algorithm.|

| ![ssr_comparison.png](https://github.com/JacobChen1998/Feature-tracking-with-PCA/blob/main/ssr_comparison.png) ![width_comparison.png](https://github.com/JacobChen1998/Feature-tracking-with-PCA/blob/main/width_comparison.png) | 
|:--:| 
| *Figure 3: Parameters compariosn before and after self-adaptation. Minimum SSR (top). Width and Height of tracked window (bottom).* |
