##polyfit在插值当中的运用
可以直接运用
`import numpy as np
x = np.arange(0,20)
y = x**2 + 4*x + np.random.randint(-5,15,20)

target = np.polyfit(x,y,2)
print(np.poly1d(target))
y1 = target[0]*x**2+target[1]*x+target[2]

import matplotlib.pyplot as plt
plt.scatter(x,y,marker = 'x',lw = 1)
plt.plot(x,y1,c = 'r')
plt.show()`