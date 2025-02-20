3d reconstruction
prev learned about scanning,  light scanning,  stereo vision etc

### Aligning Range Maps together
- we have super poisition of range maps which represents one view of a 3d object from e.g from a 3d scanner
- Problem in 3d reconstruction problem
	- how do these different range maps fit together? 
		- due to some measurement error some range maps overlaps on top of others, ideally all should be equally overlaped - the error is expected
		- if there is alot of dispersion i.e one region is not dominating of different rangmaps in disorder then thats a good sign indicating overlap on top of each other is not error but random
- coarse allignment -> fine allignment 
	-  provided the formula $\sum_{i}|Rp_i+t-q_i|$ we try to minimise the function using translation and rotation
	- we successively try to improve bit by bit
	- we find the corresponding points by proximity - assumption is that only points close enough correspond (hypothesis)
	- each iteration reduces the error of alignment  
- ICP algorithim
	```python
	kD_tree(p_i, q_i) # find closest
	min SUM R*q_i+t)²
	```

	- picking correspondence points 
		- random sampling vs normal sampling
		- (complete the ICP alogrithim with normal plane and tangen line )
- prune outliers to get appropriate errors when calculating min. another solution is to use a set of weights to determine the emphasis on a certain pair
- scans overlap partially. we can use the ourlier heurisric that is points that are not suppose to overlap does not present any meaningful correspondence and can be pruned
- ICP complete algorithim
	```python
	while not converged:
		- select some points from in source data set
		- find the nearest points from target set use (on tanget plane)
		- weight correspances
		- prune misleading points: outliers and points on boundary shape
		- use the about min formula dtermine rotation and translation
		- transform source dataset
			
		```


### Getting Closed Surfaces
- by default using triangle shape to connect the vertices is the way to go
- very difficult to get the closed surface reconstruction right because -- on very small scale it is difficult to determine the shape of the set of points how in what manner are the bound to closed
- it is appropriate to approximate the object instead of using the exact points
	- implicit function: provides a mathematical function which can determine the position of the surface e.g sine distance field (what is the distance to the surface of the object) - the function is at 0 inside is -ve and outisde is +ve
	- the function would be sampled on a regular grid like a pixel image