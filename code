
             ########## GOODWIN MODEL  ###########
             
import numpy as np
import matplotlib.pyplot as plt            

t = np.linspace(0,100,100000) # time points resolution                      
e = np.zeros(len(t)) # Pre-allocate the memory for e employment rate
W = np.zeros(len(t)) # Pre-allocate the memory for W wage share in national income

##### diff equation one parameters ###
beta = 0.1 ###capitalist
gamma = 0.05 ### labour productivity growth
n = 0.01 #### population growth 
roh = 0.5 #output/capital ratio how much output per marginal unit of capital employed

#### diff equation two parameters ######
phi = 0.05
lamdba = 0.2 

e0, W0 = 0.5, 0.5                
e[0] = e0
W[0] = W0

##### Iterative equations ######                 
for i in range(0,len(t)-1):
     dt = t[i+1] - t[i]
     e[i+1] = e[i]+e[i]*dt*((1-W[i])*roh -(beta+gamma+n))
     W[i+1] = W[i]+W[i]*dt*(-phi+lamdba*e[i]-gamma)

plt.plot(t,e,'b-', label = 'employment rate')
plt.plot(t,W,'r-', label = 'wages/national income')
plt.ylabel('share of total')
plt.xlabel('time')
plt.ylim((0,1))
plt.legend()
plt.savefig('over time.png', dpi = 300)
plt.show()
