### Review your code
Following is all code you have written by last Unit.
```python
import matplotlib.pyplot as plt
import numpy as np
plt.figure(num=1,figsize=(5,5))
x = np.linspace(-1, 1, 500)
y1 = np.sqrt(1-x**2)
y2 = -np.sqrt(1-x**2)
l1, = plt.plot(x, y1, color='blue')
l2, = plt.plot(x, y2, color='blue')
new_ticks = np.arange(-1,1,0.5)
plt.xticks(new_ticks)
plt.yticks(new_ticks)
ax = plt.gca()
ax.spines['left'].set_position(('data',0))
ax.spines['bottom'].set_position(('data',0))
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')
plt.legend(handles=[l1,l2,], labels=[r'$x^2+y^2=1$'], loc='upper right')
plt.annotate('$x$', xy=(0.98,0.5), ha='left', va='top', xycoords='axes fraction', fontsize=20)
plt.annotate('$y$', xy=(0.5,1), ha='left', va='top', xycoords='axes fraction', textcoords='offset points',fontsize=20)
plt.show()
```
### Draw a sample node
1. Take x0=-0.5 as a sample node, there are two y values correspondingly:
```python
x0=-0.5
y10 = + np.sqrt(1-x0**2)
y11 = - np.sqrt(1-x0**2)
```
2. Use `plt.scatter` to draw two dots on the circle, take following code as example:
```python
# Scatter two dots
plt.scatter(x0,y10,color='r')
plt.scatter(x0,y11,color='r')
```
3. Plot lines to the x axs and y axs for the first dot.
```python
# Plot lines
plt.plot([x0,x0],[0,y10],'k--')
plt.plot([x0,0],[y10,y10],'k--')
```
4. Use `plt.annotate` to add annotation to the first dot.
```python
plt.annotate(r'$(-0.5)^2+(%s)^2=1$' % y10, xy=(x0, y10), xycoords='data',xytext=(+30,+40),textcoords='offset points', arrowprops=dict(arrowstyle='->',connectionstyle="arc3,rad=.2"))
```
5. Following screenshot shows what you get now:
![Final Chart of a Circle](../../Linked_Image_Files/2.1_finalChart.png)
6. Add arrows onto the axis, use the `ax.annotate()`, copy following code over to variable `ax` definition:
```python
ax.annotate("",xy=(1.102,0),xytext=(-1.102,0), arrowprops=dict(arrowstyle="->"))
ax.annotate("",xy=(0,1.102),xytext=(0, -1.102), arrowprops=dict(arrowstyle="->"))
```
7. Your final plot figure shown as below:
![final figure](../../Linked_Image_Files/3_finalChart.png)
