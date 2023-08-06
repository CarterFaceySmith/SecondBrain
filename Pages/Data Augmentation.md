A classifier has to be invariant to a wide variety of transformations. So to help it, we can synthesise data simulating plausible transformations.

Examples:
- Brightness and Contrast: More robust to illumination changes
- Random Crops (and Resizing): Sometimes image only half on the picture → not showing the full image helps network to handle cropped images
	- Training random crops: Pick a random L, resize training image: short side L, randomly sample crops
	- Testing fixed set of crops: Resize image at N scales, 10 fixed crops
- Flips
- Rotations
- Combinations of the above

You should use the same data augmentation when comparing two [[Neural Networks (NN)]] (part of your network design).  

We have online and offline data augmentation. The former is done as a pre-processing step to increase the size of the dataset. The latter happens when we apply transformations in mini-batches and then feed it to the model.


See also:
- [[Data Preparation]]