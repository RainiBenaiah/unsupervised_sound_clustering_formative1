# unsupervised_sound_clustering_formative1

## Clustering Unlabeled Sound Data
This project was on clustering unlabeled audio files by using the following criteria, feature extraction, dimensionality reduction, and clustering algorithms to uncover natural groupings within sound data.

Dataset
Download the audio files from the following link and extract them:
[Download Audio Files](https://drive.google.com/file/d/1bme1IuScdIWjzFkYPOcWzFOgD50MS_zR/view?usp=sharing)

Supported audio formats:

.wav

.mp3

.flac

Steps
1. Data Loading
Extract audio files from the ZIP archive.

Automatically scan for supported audio file formats.

2. Feature Extraction
Compute MFCCs (13 coefficients per audio file).

Calculate additional features:

Spectral Centroid

Zero-Crossing Rate

Standardize all extracted features using StandardScaler.

3. Dimensionality Reduction
PCA (Principal Component Analysis): Linear technique, faster but may blurry cluster boundaries.

t-SNE (t-distributed Stochastic Neighbor Embedding): Nonlinear, provides better separation but is computationally heavier.

4. Clustering
K-Means (on PCA-reduced data): Suitable for spherical clusters, fast execution.

DBSCAN (on t-SNE-reduced data): Handles irregularly shaped clusters and noisy data effectively.

5. Evaluation
Silhouette Score: Higher values indicate better-defined clusters.

Davies-Bouldin Index: Lower values are preferred.

Results
t-SNE + DBSCAN delivered the clearest cluster separation and handled complex audio patterns better.

PCA + K-Means was significantly faster but less accurate on intricate datasets.

Usage
Run the Jupyter notebook sequentially from data loading to clustering evaluation.

Modify key parameters to fine-tune results:

n_fft (feature extraction granularity)

eps (DBSCAN epsilon)

n_clusters (K-Means cluster count)

