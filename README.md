# line
A simple python script to print a stright line, in the way that it does the matplotlib functions `plt.axhline` or `plt.axvline`, but for any line with different slopes or y intercepts.

Until now there is only a function  `line()` where we have different inputs:

* **`slope=`** (needed) The slope of the line. By default in *degrees* but it culd be im

* **`intercept=`** (needed) The y intercept value of the line.

* **`ax=`** (needed) The ax object of matplotlib where we are plotting the line i.e. `fig, ax = plt.subplots()`

* **`xdisplacement`** If we want to displace the line in the x axe

* **`mode`** Mode of slope input. By default is `'degree'`, could be changed by `'radian'` or `'slope'`

* **`color`** The color of the line


For installing it you can do:

```
import httpimport
with httpimport.remote_repo(['line'], 'https://raw.githubusercontent.com/juanjq/lines/main'):
     import line
```

An example of use,

```
fig, ax = plt.subplots()

#other random plot
x1 = np.linspace(-1,1,100)
ax.plot(x1, np.sin(x1))

#plot the line
line.line(20,0.5,ax,xdisplacement=-0.6,color='darkblue',linestyle='--')

plt.show() 
```

![alt text](https://github.com/juanjq/line_plot/blob/main/data/line.png?raw=true)


# regression
Script for linear and plynomial regression simple graph plotting. For installing it you could do:

```
import httpimport
with httpimport.remote_repo(['regression'],'https://raw.githubusercontent.com/juanjq/lines/main'):
    import regression as reg
```

There are two classes `Linear` and `Polynomial` an there ara some examples of use,

* **Linear regression**

```
linreg = reg.Linear(xdata,ydata)

#print results
linreg.results()

#get values 
A,uA = linreg.A,linreg.uA
B,uB = linreg.B,linreg.uB
R    = linreg.R


fig, ax = plt.subplots()
plt.plot(x,y,'.r')

#plot the line
linreg.plot(ax, color = 'darkblue',linestyle = '-.')

plt.show()
```
![alt text](https://github.com/juanjq/lines/blob/main/data/lin.png?raw=true)


* **Polynomial fit**

```
polreg=reg.Polynomial(xdata,ydata,degree = 3)

#print results
polreg.results()

#get coefficients 
coeficients = polreg.coefs()
print(coeficients)


fig, ax = plt.subplots()
plt.plot(x,y,'.r')

#plot the polynomial
polreg.plot(ax,color = 'darkblue',linestyle = '-.')

plt.show()
```
![alt text](https://github.com/juanjq/lines/blob/main/data/pol.png?raw=true)

Scheme of the classes and functions and attributes f the classes,

![alt text](https://github.com/juanjq/lines/blob/main/data/scheme.jpeg?raw=true)
