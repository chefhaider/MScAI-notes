
**Discriminant Analysis** is a statistical technique used in pattern recognition and machine learning to classify observations into predefined categories based on predictor variables. The main goal is to find a set of linear combinations of the predictor variables that best separate the categories.


Gaussian classifier Properties
- decision boundary is quadratic
- classes same covariance -> decision boundary is linear
- covariance matrices are diagonal -> Naive Bayes Classifier
- covariance matrix is sum and priors are identical -> classification requires minimisation of **Mahalanbois distance** 
- covariance matrices are identitiy -> Nearest Neighbour Classifier  
- Regularized covariate matrices -> compromise between quadratic and linear boundaries

---


Feature Transforms are applied to hit one or more of these points: 

- Transform the features in a space where they are normally distributed with a Identity Matrix as the Covariance Matrix (To get the NN-Classifier !) - because this implies that features are uncorrelated which leads to better learning for NN, especially when features are normally distributed
- transform the features in a higher dimensional space, where the decision Boundary is linear
- transform the features in a subspace where the classification problem can be solved sufficiently


Achieving Identity Matrix as covariance
- using SVD for covrariance matrix on gaussian classifier (*see formulation*)
- properties
	- decision boundray in linear
	- all classes y share the same covriance matrix
	- we can compute the covraince matrix such taht all covriance matrix are identity matrix

Linear Discriminant Analysis
(*see formulation*)
- maximisez separability between the groups - aims to find the axes that maximize the separation between different classes
- we can use lda to compress our feature space, after transformaiton we still have the values on the orthogonal line and this does not effects the decsion boundary wrt to the features
- class centrios span (k-1) dimensional subspace, 


Ranked Reduced Linear Discriminant Analysis
- calculate PCA of covariance of mean vectors
- computes linear funciton phi that projects a high spread of features
- we apply langrange multiplier to the methode of mamimisation of phi
