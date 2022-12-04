# Dimintion-reduction
# Using t-SNE to reduce the dimensionality to two dimensions
 Use t-SNE to reduce the MNIST dataset down to two dimensions and plot the result using Matplotlib. You can use a scatterplot using 10 different colors to represent each image's target class
 Dimensionality reduction on the full 60,000 images takes a very long time, so let's only do this on a random subset of 5,000 images
 save the data to disk so that we can fetch it fast if we need it using the next cell
 use Matplotlib's scatter() function to plot a scatterplot, using a different color for each digit
 # Labelling the Clusters
 focusing on three digits that show more overlapped, running t-SNE on these 3 digits and now the clusters have far less overlap
 # create a plot_digits() function that will draw a scatterplot 
 using PCA. We will also time how long it takes, and PCA is blazingly fast! But although we do see a few clusters, there's way too much overlap.try LLE
 # Using other dimensionality reduction algorithms such as LLE, MDS and t-SNE
  LLE, i.e. Local Linear Embedding which is part of the mainfold class of sklearn.LLE took 2.9s.now we apply PCA first, preserving 95% of the variance.took 3.4s.
  The result is more or less the same, but this time it was almost 4× faster.try MDS.took 226.3s.This does not look great, all clusters overlap too much.try PCA before MDS.took 246.6s.Same result, and no speedup: PCA did not help.try LDA.took 1.2s. is very fast, and it looks nice at first, until you realize that several clusters overlap severely.t_SNE took 48.1s.It's twice slower than LLE, but still much faster than MDS, and the result looks great
