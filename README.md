# AI-ML-internship-task-13
The Core Problem: The Curse of Dimensionality
When we work with images (like MNIST digits), every single pixel is a "feature." For a 28 \times 28 image, that is 784 dimensions.
The Problem: High-dimensional data is computationally expensive, difficult to visualize, and often contains "noise" (pixels that don't help identify the digit).
The Solution: PCA reduces these 784 features into a few "Principal Components" that capture the most important patterns.
2. How PCA Works (Step-by-Step)
PCA doesn't just "delete" columns; it creates new ones using these mathematical steps:
Standardization: The data is scaled so that each feature has a mean of 0 and a variance of 1.
Covariance Matrix Computation: We calculate how much the dimensions vary from the mean with respect to each other.
Eigenvectors & Eigenvalues: We calculate the "Eigenvectors" (the directions of the data) and "Eigenvalues" (the magnitude/strength of those directions).
Principal Components: We sort the Eigenvectors by their Eigenvalues. The one with the highest Eigenvalue is Principal Component 1 (PC1)—it holds the most information.
3. Key Concepts Defined
Explained Variance Ratio
This is a percentage that tells you how much of the original dataset's "information" is stored in each component.
If PC1 has an explained variance of 0.40, it means 40% of the entire dataset's variability is compressed into that one single component.
The "Elbow" Method
When plotting cumulative variance, we look for an "elbow" in the graph. This is the point where adding more components gives "diminishing returns" (very little extra information).
4. Comparison: PCA vs. Feature Selection
It is a common interview trap to confuse these two:
Feature Selection: You simply pick the "best" existing features (e.g., "I'll only look at the center 10 pixels of the image").
PCA (Feature Extraction): You combine all pixels into brand new variables. No original pixel is "kept" in its raw form; they are all blended into the components.
5. Task-Specific Analysis (MNIST/Digits)
In this specific task, you are observing:
Compression: How we can represent a digit using only 10 numbers instead of 64 (or 784).
Visualization: Humans cannot see in 64D. By reducing the data to 2D using PCA, we can create a scatter plot where different digits (0s, 1s, 2s) form distinct clusters.
Efficiency: Training a Logistic Regression model on 30 PCA components is significantly faster than training on the full raw dataset, often with negligible loss in accuracy.
