# Vessel-Filtering
Ground truth data, noisy data and filtering algorithms

# goal of this Git
Create a filtering algorithm that filters the noisy data of a vessel model in real time! 

A ground truth training data set is provided in the form of a matrix M1:

M1=   t0,y,psi,u,v,r,Fx,Fy,Fz;
      | ,|,|  ,|,|,|,| ,| ,| ;
    tend,y,psi,u,v,r,Fx,Fy,Fz;

This matrix consist of 10k rows.

The measurable states are x, y, psi. A noisy data set of measurements M2 is created by taking the first three collumns of M1 and adding white noise to it:

M2 = M1(col1, col2, col3)  + noise(size(M1(col1, col2, col3))

Now create an online filter, such that when a measurement is received, it filters out the noise. The performance of the filter is checked by summing the two norm of the error between the ground truth data and the filtered states of states (x,y,psi,u,v,r) for the last 3k of data points. 
