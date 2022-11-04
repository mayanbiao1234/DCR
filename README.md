# **Curvature-Balanced Feature Manifold Learning for Long-Tailed Classification**

In Section 3 we propose measures for the perceptual manifold's volume, separation, and curvature. We provide the pseudo-code below to show how to apply these methods in practice. Our approach can be applied not only to calculate the geometric properties of feature manifolds but also to the image space. In addition to image data, other types of data also obey the manifold distribution law, so our method can be employed to evaluate them as well.

**1. Pseudocode for The Volume of Perceptual Manifold.**

We give the calculation procedure of perceptual manifold volume in Algorithm 2. In addition, the volume of the data manifold can also be calculated directly in image space (Algorithm 3). Unlike the method for calculating the volume of the perceptual manifold, it is necessary to shrink and flatten the image into vectors. The reason for this is that the dimensionality of the image space is often very high, so we alleviate the dimensionality catastrophe by simply downsampling the dimensions.

![image](https://user-images.githubusercontent.com/31196857/199918189-f0702dd2-4dbb-4236-af64-a0ec206b57a6.png)

**2. Pseudocode for The Separation Degree of Perceptual Manifold.**

The distributions of different classes are far from each other to give the model higher discriminative power. Euclidean distance or cosine distance between class centers is often used as the measure of distance between classes, and these two distances are also commonly used as loss functions when constructing sample pairs. However, maximizing the distance between proxy points or samples does not keep one class away from all the remaining classes at the same time, and the distance between class centers does not reflect the degree of overlap of distributions.

Therefore, we define the degree of separation of the perceptual manifold based on the volume of the perceptual manifold, which is applicable to the case of multiple perceptual manifolds and is an asymmetric measure. Algorithm 4 shows in detail how to calculate the degree of separation of the perceptual manifold in practice. 

![image](https://user-images.githubusercontent.com/31196857/199918914-def07599-0f27-4c29-8e6d-29caf7473c8a.png)

**3. Pseudocode for the Mean Gaussian Curvature of The Perceptual Manifold.**

The complexity of the perceptual manifold reflects the extraction ability of the deep neural network for the input image. [1] proposed to decompose the manifold into multiple pieces, each of which is homogeneously mapped to a linear space, and the lower limit of the number of pieces in all decomposition methods defines the complexity of the manifold. However, there is no way to know the quantitative expression of the point cloud perceptual manifold, and it is difficult to find its homogeneous mapping. 

We give the analytical solution for estimating the curvature of the perceptual manifold in Section 3.4, but the whole derivation process is complicated. Therefore, we clearly list the steps for calculating the curvature of the perceptual manifold in Algorithm 5, so that it can be easily understood and used by other researchers.

![image](https://user-images.githubusercontent.com/31196857/199919448-ad36618f-bc52-4187-8fb8-3e4994523dbe.png)
