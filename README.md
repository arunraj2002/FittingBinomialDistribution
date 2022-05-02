# Fitting Binomial Distribution

# Aim : 

To fit binomial distribution for the given frequencey distribution

![image](https://user-images.githubusercontent.com/104613195/165903525-d4a642fc-ae42-476c-842f-bec7f72987c8.png)

# Software required :  

Python

# Theory:

The binomial distribution is a discrete probability distribution. It describes the outcome of n independent trials in an experiment. Each trial is assumed to have only two outcomes, either success or failure. If the probability of a successful trial is p, then the probability of having x successful outcomes in an experiment of n independent trials is as follows.

![image](https://user-images.githubusercontent.com/104613195/165905146-30e5b86e-4159-41a3-aa6d-885204c2e36a.png)

The following are criteria for a frequency distribution to be a binomial distribution
1. The experiment consists of n repeated trials.
2. Each trial can result in just two possible outcomes (a success anda failure).
3. The trials are independent (the outcome on one trial does not affect the outcome on other trials).
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166250867-46571ef5-f77b-4658-86ce-1c60c52fdfb1.png)

# Program
## Program
## Developed by
## Register Number: 212220230004
## Name: R Arunraj
```python
import numpy as np
import math
import scipy.stats
X=[0,1,2,3,4,5,6]
f=[153,169,72,31,12,6,2]
n=6
N=np.sum(f)
mean=np.inner(X,f)/N
Pr=list(); E=list(); xi=list()
print("  X P(X=x) Obs.Fr  Ex.Fre   xi ")
print("----------------------------------")
for x in range(7):
    Pr.append(math.exp(-mean)mean*x/math.factorial(x))
    E.append(Pr[x]*N)
    xi.append((f[x]-E[x])**2/E[x])
    print("%2.2f %2.2f  %4.2f   %3.2f  %3.2f"%(x,Pr[x],f[x],E[x],xi[x]))
print("----------------------------------")
cal_chi2=np.sum(xi)
print("Calculated value of Chi square is %4.2f"%cal_chi2)
tab_chi2=scipy.stats.chi2.ppf(1-.01, df=n)
print("Table value of Chi square at 1  level is %4.2f"%tab_chi2)
if cal_chi2<tab_chi2:
    print("The given data can be fitted in Poissson distribution at 1% LOS")
else:
    print("The given data cannot be fitted in Poisson distribution at 1% LOS")
 ```
 
 # Output:
![output](https://user-images.githubusercontent.com/75235747/166327244-5c5ee2d9-059b-4c76-a004-62adb054e02b.JPG)


# Results:
Thus, fitting poisson distribution for the given frequencey distribution is verified.
