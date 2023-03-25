# A shortcut for Coding in Python
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