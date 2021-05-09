This is how you can define a piecewise function in numpy:

```python
import numpy as np
import matplotlib.pyplot as plt


def piecewise(t):
    conds = [ 
        t <= -1, 
        (-1 < t) & (t <= 1),
        (1 < t) & (t <= 5),
        t > 5
    ]
    funcs = [
        lambda t: 0, 
        lambda t: t + 1, 
        lambda t: 4 - 2*t, 
        lambda t: 0
    ]
    return np.piecewise(t, conds, funcs)

t = np.arange(-2, 6, 0.01)
plt.xlabel('t')
plt.ylabel('y(t)')
plt.plot(t, piecewise(t))
plt.show() # or plt.savefig('my_fig.png')
```
