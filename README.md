# SIG

## Pseudobulk Analysis

    res = pd.DataFrame(columns=adata.var_names, index=adata.obs['leiden'].cat.categories)                                                                                                
    for clust in adata.obs.leiden.cat.categories: 
    res.loc[clust] = adata[adata.obs['leiden'].isin([clust]),:].X.mean(0)
    
    res.T.to_csv("Dendritic_control_counts_Average_genexpression_percluster.csv")
    
**be carefull with the varible on adata.X, for recovering counts use adata.X=adata.layers["counts"]**
