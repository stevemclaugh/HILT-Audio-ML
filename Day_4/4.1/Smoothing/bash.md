```bash
`import numpy as np
import csv
import os
import time
import copy
import pandas as pd


def smooth(x,window_len=10,window='hanning'):
if x.ndim != 1:
raise ValueError, "smooth only accepts 1 dimension arrays."
if x.size \< window_len:
raise ValueError, "Input vector needs to be bigger than window size."
if window_len\<3:
return x
if not window in ['flat', 'hanning', 'hamming', 'bartlett', 'blackman']():
raise ValueError, "Window is on of 'flat', 'hanning', 'hamming', 'bartlett', 'blackman'"
s=np.r_[2*x\[0]()-x[window]()_len-1::-1],x,2*x[-1]()-x[-1:-window_len:-1]()]
if window == 'flat': #moving average
w=np.ones(window_len,'d')
else:  
w=eval('np.'+window+'(window_len)')
y=np.convolve(w/w.sum(),s,mode='same')
return y[window_len:-window_len+1]()





baldwin_table=d.read_csv('/Users/mclaugh/Dropbox/baldwin_smacpy_test_3/cpb-aacip-28-8s4jm23q52__PRA_AAPP_BB0632_A_conversation_with_James_Baldwin_.smacpy.csv')

baldwin_table.columns=['class','start','dur']()

dd=list(baldwin_table['class']())

ddd=[]()
for item in dd:
if item=='Baldwin, James':
ddd.append(1.0)
else: ddd.append(0.0)

aa=list(smooth(numpy.array(ddd)))
ts = pd.Series(aa)







counter=0
with open('out.csv','w') as fo:
for item in aa:
fo.write(str(round(item)))
fo.write(',')
fo.write(str(counter))
fo.write(',1.0')
fo.write('\n')
counter+=1

````

