# Facial Recognition through **'Eigenfaces'**


The "Eigenfaces" algorithm works by projecting face images onto a subspace of principal components (eigenfaces) and classifying an unknown face by comparing it to known faces based on the minimum distance between projections. The goal is to determine whether the face matches an individual in a dataset. <br>
A dataset of 40 individuals was considered (not available in the repository), each with 10 available images. It was divided into a training set and a test set by partitioning the images into two subsets, selecting k images per subject for training and 10-k for testing.

<br><br>

### Training phase:
The implementation is based on principal component analysis. Each image is treated as a vector in an $R^N$ space, where N is the number of pixels (rows × columns). The principal components are then computed, which correspond to the eigenvectors of the covariance matrix in $R^{N \times N}$ of the centered image vectors. The training images will be firstly centerd $Φ_l=f_l- \hat{f}$ (where $\hat{f}$ is the mean face), and the covariance matrix will be $C=\frac{1}{L} ΦΦ^T$. Since the number of images (L) is smaller than the dimensions of the space (N×N), there will be only L significant eigenvectors ${v_1,…,v_L}$, while the remaining eigenvectors will have associated eigenvalues equal to zero. Subsequently, the images are projected onto a smaller subspace generated only by the first L′ selected principal components ${v_1,…,v_L′}$, known as the "eigenfaces" space U.

<br><br>


### Test phase:
The automatic face recognition procedure follows. A new image $f_{new}$​ from the test set is first centered $Φ_{new}=f_{new}−\hat{f}$, then $Φ_{new}$​ is projected onto the eigenface subspace U, and the Euclidean distance $ϵ$ between $Φ_{new}$​ and its projection $UU^TΦ_{new}$​ is computed.


