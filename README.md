# Face Reenactment Algorithm Evaluation

To evaluate the generated frames of your face reenactment algorithm, please follow the instructions below:

## Dataset Access

1. Access the dataset required for evaluation using the provided [Google link](https://drive.google.com/drive/folders/1RnPOTsH3t3j8zVLaKbPu-YMJBhevV5J4?usp=sharing). This link will direct you to a folder containing the necessary files, including source images, driving videos, and ground-truth videos or images.

2. Download the dataset files to your local machine for evaluation.

## Input Format Selection

Choose the appropriate input format based on the requirements of your algorithm:

- If your algorithm accepts video inputs, you can utilize the driving videos provided in the dataset.
- If your algorithm accepts individual frames, you can utilize the corresponding frames from the dataset.

## Evaluation for Pitch Negative Rotation

To evaluate your method for pitchNegative rotation, follow these steps:

1. Use "source.jpeg" as the source image.

2. Utilize the content in the "3D_real_head_dataset/videos/driver" folder as the driving videos.

3. Save frames belonging to the same video under the same folder.

   For example, if you are driving the source frame by the "pitchNegative_id122" video, save your resulting frames in the "pitchNegative_id212_reenacted_by_id122" folder.

4. Use the following scripts to compute different metric scores on the generated images and ground truth:

   - Use `compute_SSIM.ipynb` to compute the Structural Similarity Index (SSIM).
   - Use `compute_CSIM.ipynb` to compute the Cosine Similarity (CSIM).
   - Use `compute_AKD.ipynb` to compute the Average Keypoint Distance (AKD).

   **Note:** Set up a separate environment for each evaluation script to avoid conflicts. The required libraries for each script are as follows:
   - `compute_SSIM.ipynb` requires `scikit-image (skimage)`, `pandas`, `PIL`, and `OpenCV (cv2)`.
   - `compute_CSIM.ipynb` requires the `deepface` library.
   - `compute_AKD.ipynb` requires `pandas`, `OpenCV (cv2)`, and `MediaPipe`.

## Additional Information

Please note the following additional information:

- The identity of the source image in the FaceScape dataset is 212, and we use identities 122, 340, 344, and 359 to reenact the source frame.

- It is recommended to use a different environment for each evaluation script to avoid conflicts and ensure the required libraries are available.
