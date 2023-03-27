# Shortcuts for  ML Coding in Python
``` python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

import warnings
warnings.filterwarnings('ignore')
```
## PCA
``` python
# Create cumulative explained variance graph
# Pretend we'd like to have about 90% explained variance
from sklearn.decomposition import PCA

pca = PCA()
pca.fit(df)

cum_explained_variance = np.cumsum(pca.explained_variance_ratio_)
plt.plot(cum_explained_variance)
plt.xlabel('PC number')
plt.ylabel('% Cumulative explained variance')
```
``` python
# Find the first 100 principle components of the dataset
pca = PCA(n_components=100)
pca.fit(df)

# Transform the data to its low-dimensional representation
reduced_df = pca.transform(df)

print(reduced_df.shape)
pd.DataFrame(reduced_df).head() #as a dataframe
```
``` python
cum_explained_variance = np.cumsum(pca.explained_variance_ratio_)
plt.plot(cum_explained_variance)
plt.xlabel('PC number')
plt.ylabel('% Cumulative explained variance')
```

``` python
# Get the actual PCs from the sklearn PCA model
PCs = pca.components_
print('PC matrix shape: {}'.format(PCs.shape))
pd.DataFrame(PCs).head()
```
## Silhouette Score
To choose K in Unsupervised Learning for K-means method, we use the following Code:
``` python
from sklearn.metrics import silhouette_score

km = KMeans(n_clusters = 5)
km.fit(X)
silhouette_score(X, km.labels_)
```