# Surface Characterization
In this project, we present a discrete surface characterization method based on the extraction of the top k eigenvalues of the Laplace-Beltrami. The project consists of three main parts: Data preparation, Geometric feature extraction and Shape classification. For the data preparation, we cleaned and remeshed well known 3D shape models datasets, in particular, we process meshes from ModelNet10, ModelNet40 and Thingi10k. The geometric feature extraction is based on the “Shape DNA” for triangular meshes introduced by Reuter, et al., we compute the Laplace-Beltrami operator for triangular meshes using the robust-laplacian python library. 

# Data preparation 
The datasets used for the shape classification are:

**1. ModelNet10**: This dataset is a subset of the larger ModelNet40 dataset, which contains 40 categories of 3D shapes. ModelNet10 has 4,899 shapes from 10 categories, such as bathtub, bed, chair, desk, etc. The shapes are pre-aligned and normalized to fit in a unit cube. The dataset has a standard split of 3,991 shapes for training and 908 shapes for testing.

**2. ModelNet40:** This dataset is one of the most widely used benchmarks for shape classification. It has 12,311 shapes from 40 categories, such as airplane, car, plant, lamp, etc. The shapes are also pre-aligned and normalized. The dataset has a standard split of 9,843 shapes for training and 2,468 shapes for testing. 

**3. Thingi10k:** This dataset is a collection of 10,000 models from featured "things" on thingiverse.com, which is a popular website for sharing 3D printing models. Thingi10k is a large scale dataset that captures the variety, complexity and quality of real-world 3D models. The dataset has 72 categories and 99.6% of the models are in .stl format.

For this project, we decided to use a subset of the ModelNet10 dataset to perform some preprocessing steps on the meshes and apply a surface classification algorithm. We aimed to classify surfaces based on their spectral properties using two different datasets: a synthetic one and ModeNet10. For the classification task, we first used the trimesh library (open3D can be used but there are more shapes in the trimesh library) to generate some simple shapes for our synthetic dataset and remeshed each generated mesh. The generated data consisted of 6 classes with 50 samples each. The shapes include Annulus, Box, Capsule, Cone, Cylinder, Sphere. The first 30 eigen values were computed similar to the ModelNet dataset in order to perform some sanity checks and a fair comparison between the two datasets. In total, we took 225 samples for the training set and 75 samples for the testing set. 

For the ModelNet10 dataset we selected 50 meshes for the training set and 25 meshes for the testing set per class. In total, we took 500 meshes for the training set and 250 meshes for the testing set. After experimenting with different machine learning algorithms, the validation results for both datasets.  We first experimented with simple machine learning algorithms like Naive Bayes, KNN, Random Forest, Decision Trees, Gradient Boosting and more from the sklearn library. Then we experimented with the sequential model Bidirectional LSTM using the pytorch library to try and improve the results. The metric used for the evaluation procedure is accuracy. 






