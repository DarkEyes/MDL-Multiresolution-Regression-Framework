# MDL-Multiresolution-Regression-Framework

Welcome

To run the code, please open "MDLResFramework3_EXP.Rmd" via RStudio.
Then, go to the chunk "Code running block" and follow the instructions.
The main function of our framework is "FindMaxHomoPartition(DataT,gamma)".

- INPUT: DataT$X[i,j] is the value of jth independent variable of ith individual. 
- INPUT: DataT$Y[i] is the value of dependent variable of ith individual. 
- INPUT: DataT$clsLayer[i,k] is the cluster label of ith individual in kth cluster layer.

- OUTPUT: Copt[p,1] is equal to k means a cluster that is a pth member of the maximal homogeneous partition is at kth layer and the cluster name in kth layer is Copt[p,2]
- OUTPUT: Copt[p,3] is "Model Information Reduction Ratio" of pth member of the maximal homogeneous partition: positive means the linear model is better than the null model.
- OUTPUT: Copt[p,4] is $$R^2(C)_{\text{cv}}$$  of pth member of the maximal homogeneous partition. The greater Copt[p,4], the higher homoheneous degree of this cluster.
- OUTPUT: models[[k]][[j]] is the linear regression model of jth cluster in kth layer.
- OUTPUT: models[[k]][[j]]$clustInfoRecRatio is the "Cluster Information Reduction Ratio" between the jth cluster in kth layer and its children clusters in (k+1)th layer: positive means current cluster is better than its children clusters. Hence, we should keep this cluster at the member of maximal homogeneous partition instead of its children. 
