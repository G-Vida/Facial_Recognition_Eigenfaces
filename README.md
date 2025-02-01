# Facial Recognition through **'Eigenfaces'**


The "Eigenfaces" algorithm works by projecting face images onto a subspace of principal components (eigenfaces) and classifying an unknown face by comparing it to known faces based on the minimum distance between projections. The goal is to determine whether the face matches an individual in a dataset. <br>
A dataset of 40 individuals was considered (not available in the repository), each with 10 available images. It was divided into a training set and a test set by partitioning the images into two subsets, selecting k images per subject for training and 10-k for testing.

<br><br>

###Training phase:
The implementation is based on principal component analysis. Each image is treated as a vector in an $R^N$ space, where N is the number of pixels (rows × columns). The principal components are then computed, which correspond to the eigenvectors of the covariance matrix in $R^{N \times N}$ of the centered image vectors. The covariance matrix will be $C=\frac{1/L} ΦΦ^T$. Since the number of images (LL) is smaller than the dimensions of the space (RN×NRN×N), there will be only LL significant eigenvectors {v1,…,vL}{v1​,…,vL​} instead of N2N2, while the remaining eigenvectors will have associated eigenvalues equal to zero.





