Analysis Overview
=================

This page describes the different analysis types that can be performed using
`gs2_correlation`, as well as additional useful features.

Perpendicular Correlation
-------------------------

In GS2, fields are written out as a function of kx and ky. This allows the use
of the Wiener-Khinchin theorem in 2D to calculate the correlation function:

.. math:: C(\Delta x, \Delta y) = IFFT2[|f(k_x, k_y)|^2]

where C is the correlation function, *f* is the field, and IFFT2 is the 2D 
inverse Fourier transform. Briefly, the perpendicular correlation analysis
performs the following:

* Calculates the 2D correlation function using the WK theorem.
* Splits the correlation function into time windows (of length *time_slice*, 
  as specified in the configuration file).
* Time averages those windows and fits them with a tilted Gaussian to find the
  correlation parameters lx, ly, kx, ky, theta.
* Writes correlation parameters into a csv file, with one row per time window.
* Generates and saves various plots of the true and fitted correlation functions.

Time Correlation
----------------

Create a Film
-------------

Zonal Flows
-----------

