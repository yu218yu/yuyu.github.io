# 插值和拟合

```
python
import numpy as np
x = np.arange(0,20)
y = x**2 + 4*x + np.random.randint(-5,15,20)

target = np.polyfit(x,y,2)
print(np.poly1d(target))
y1 = target[0]*x**2+target[1]*x+target[2]

import matplotlib.pyplot as plt
plt.scatter(x,y,marker = 'x',lw = 1)
plt.plot(x,y1,c = 'r')
plt.show()

```
以下为插值拟合的完整代码
包括了polyfit和curve_fit


```
python

import numpy as np
from scipy.optimize import curve_fit
x = np.arange(0,20)
y = x**2 + 4*x + np.random.randint(-5,15,20)

target = np.polyfit(x,y,2)
print(np.poly1d(target))
y1 = target[0]*x**2+target[1]*x+target[2]

def fun(x,a,b,c):
    return a*x**2 + b*x +c

popt,_ = curve_fit(fun,x,y,[1,1,1])
print(popt)
y2 = fun(x,*popt)

import matplotlib.pyplot as plt

fig,(ax1,ax2,ax3) = plt.subplots(1,3,figsize=(10,8))
ax1.scatter(x,y,marker = 'x',lw = 1)
ax2.scatter(x,y,marker = 'x',lw = 0.5)
ax2.plot(x,y1,c = 'r')
ax3.scatter(x,y,marker = 'x',lw = 0.5)
ax3.plot(x,y2,c = 'green')
plt.show()
import numpy as np
from scipy.optimize import curve_fit
x = np.arange(0,20)
y = x**2 + 4*x + np.random.randint(-5,15,20)

target = np.polyfit(x,y,2)
print(np.poly1d(target))
y1 = target[0]*x**2+target[1]*x+target[2]

def fun(x,a,b,c):
    return a*x**2 + b*x +c

popt,_ = curve_fit(fun,x,y,[1,1,1])
print(popt)
y2 = fun(x,*popt)

import matplotlib.pyplot as plt

fig,(ax1,ax2,ax3) = plt.subplots(1,3,figsize=(10,8))
ax1.scatter(x,y,marker = 'x',lw = 1)
ax2.scatter(x,y,marker = 'x',lw = 0.5)
ax2.plot(x,y1,c = 'r')
ax3.scatter(x,y,marker = 'x',lw = 0.5)
ax3.plot(x,y2,c = 'green')



plt.show()

```

## 结果如下
<img width="647" height="517" alt="Image" src="https://github.com/user-attachments/assets/2a5bb7eb-58da-4bfd-9725-79f4ea88dbc7" />