# Import Libraries


```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```


```python
print("help")
```

# Load the Data


```python
gene_expression_file = "data/PAAD_mmrna_log2_tpm_transformed.csv"

```

# Table


```python
# LDHA expression values across all samples
"LDHA" in filtered_data.index:    ldha_table = filtered_data.loc["LDHA"]
    print("\nLDHA Expression Table:")
    display(ldha_table.to_frame(name="LDHA Expression"))

```

# Graph


```python
# Define the genes of interest
selected_genes = ["LDHA"]

# Filter
filtered_data = data[data[gene_column].isin(selected_genes)]

# genes as rows and samples as columns
filtered_data = filtered_data.set_index(gene_column)

# Calculate the correlation matrix
correlation_matrix = filtered_data.T.corr()

# Plot the heatmap for co-expression analysis
plt.figure(figsize=(15, 12))
sns.heatmap(correlation_matrix, annot=True, cmap="coolwarm", fmt=".2f", cbar=True)
plt.title("Co-expression Heatmap of Selected Genes")
plt.show()

```


```python

```
