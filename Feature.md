A feature in data science is an individual property of some input entity. Common examples include average brightness of an image, presence of a certain word in text, or the length of a video.

Often more than one feature is used for later techniques such as classification. In this case, the features are combined into a single feature vector, which constructs a vector space of the features called the feature space. 
This can lead to geometric interpretations of statistical techniques.

# Types of feature
Features can be organised into different types, basaed on the type of data they are encoded with:
- Primitive (Quantitative) - numerical data, that can be further defined as either discrete or continuous
- Semantic (Nominal/Qualitative) - data that describes some quality of an entity
- Ordinal - data that can be used to order based on some property
- Statistical - a statistical measure of the data set, such as mean or [[standard deviation#Variance|variance]].

# Feature dimensionality
The number of dimensions of the feature space is referred to as the dimensionality. 
As dimensionality increases, the spatial density of a data set reduces, because the same data is split between a n increasing volume.
Therefore, it is beneficial to reduce the number of features. This can be done by feature selection, whereby the most useful features are used and the rest discarded, or feature extraction, where the data is projected into a lower dimensional space.

## Feature selection
Feature selection cannot be done exhaustively, as the set of possible subsets of size $d$ given $N$ original features has the cardinality $\cfrac{N!}{(N-d)!d!}$. Instead, one of two techniques is usually employed - forward or backward stepwise selection.
Forward stepwise selection begins with a null model - one with no features, and incrementally adds the most significant feature from the data set until $d$ features have been selected. 
Backward stepwise selection starts with a full model that contains every feature of the data, and iteratively removes the least significant until only $d$ features remain.
Features are assessed by significance tests. Stepwise selection assumes that all features are independent.

## Feature extraction
Feature extraction finds a mapping from the original feature space to a reduced dimensional vector space: given a feature space $\mathbb R^N$ with feature vectors $\mathbf m$, a mapping $\mathbf x = \phi(\mathbf m) : \mathbb R^N \to \mathbb R^d$ can be constructed that preserves as much of the information encoded in the original vector space as possible.
One strategy for generating this mapping is [[principal component analysis]].
