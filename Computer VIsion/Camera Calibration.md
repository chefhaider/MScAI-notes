

 - Least Squares Extrinsic paramters, and  intrinsic parameters
	 - 6 intrinsic and 5 extrensic parameters

 - for projective transfromation we need the homogenous space, if we need to go back to 2d space we need to divide the x, y with w (third homogenous component)

### camera (projection) matrix

calibration phatnom, constructed by design if you know the 3d points,  and from 2d points and given enough of these pairs, calibration points can be calculated -

problem with least squares methode y=mx +b is it fails for vertical lines because then m=>inf
fix ax+by+c i.e hessian normal form