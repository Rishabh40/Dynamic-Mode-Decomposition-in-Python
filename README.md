    PROJECT DESCRIPTION
An Intelligent Transportation System forms an integral component of a smart city. Formulation of traffic policy and well regulated traffic 
operation facilitates smooth mobility behaviour in the city. Traffic volume prediction is a challenging research field when the whole city
is concerned. Our goal is to best approximate the prediction at multiple source and destination pairs of the city and for few time steps 
ahead in the future. We look at the best utilisation of the available resources to improve the prediction. For our objective, we would look
into some feature engineering techniques like dimensionality reduction, data-imputation and data-analysis concept like classification, 
clustering etc and few matrix based concepts SVD, PCA etc. A forecasting concepts using DMD.

    Singular Value Decomposition
Let X be a real or complex m x n  matrix which can be decomposed by using SVD in form of X=UΣV-1 Where U is the Eigen matrix of XX-1, 
V is the eigen matrix of X-1X and Σ be the diagonal matrix of singular values of X which can be calculated by taking square root of eigen 
values of either XX-1 or X-1X. XX-1(mxm)=UΣ2U-1 Comparing it with standard eigen decomposition we can observe that Σ is the square root of 
eigen values of XX-1. X-1X(nxn)=VΣ2V-1 Comparing it with standard eigen decomposition we can observe that Σ is the square root of eigen 
values of X-1X.

    Principal Component Analysis
The idea of principal component analysis (PCA) is to reduced the reductancy and noise of a data set consisting of many variables correlated
with each other. First we construct a covariance matrix whose diagonal elements are variance measures and rest of elements are covariance
measures Cx=(1/(n-1))*XX-1 Where X is our data matrix.Variance can be computed by using this formula σx2=(1/(n-1))*xxT And covariance 
between two vectors can be computed by using this formula σxy2=(1/(n-1))*xyT And our aim is to make the covariance matrix such that it’s 
non-diagonal elements reduces to zero, this will help us to kill out all the related data in original data set. We can do this by 
transforming Original data matrix with respect to UT.

    Dynamic Mode Decomposition
Let X be the given data from which we have to predict the future data which is X’. Then we can define a matrix A which will help us to 
predict future results.
       X’=AX
       X=UΣV-1
       X’=AUΣV-1
       U-1X’VΣ-1=U-1AU=Ă
       ĂW=W∧
       X’VΣ-1ĂW=X’VΣ-1W∧
       (X’VΣ-1U-1)(X’VΣ-1W)=(X’VΣ-1W)∧
       X’X-1(X’VΣ-1W)=(X’VΣ-1W)∧
       AΦ=Φ∧
We have not directly computed A because of computation efficiency instead we computed Ă Which can be computed with much lesser 
computation, and we will predict future results using eigen decomposition of A for which we will be needed With the eigenvalues and 
eigenvectors of A. For this purpose we take eigenvalue of A as ∧(the eigen values of Ă), and we can observe from previous slide if we 
do so eigen vectors of A will be Φ=X’VΣ-1W. We are using DMD approach because it is a data driven technique.







