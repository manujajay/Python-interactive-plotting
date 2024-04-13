# Advanced and Interactive Charting with Python

This README provides detailed instructions and code samples for creating advanced and interactive charts using popular Python libraries such as Plotly, Matplotlib, and Bokeh.

## 1. Plotly

Plotly is a library that allows for complex, interactive plotting. It supports 3D charts and dynamic updates, making it suitable for web-based dashboards.

### Installation

```bash
pip install plotly
```

### Example: 3D Surface Plot

```python
import plotly.graph_objects as go

z_data = [[z1, z2, z3, ...], [z1, z2, z3, ...], ...]
fig = go.Figure(data=[go.Surface(z=z_data)])
fig.update_layout(title='3D Surface Plot', autosize=False,
                  width=500, height=500,
                  margin=dict(l=65, r=50, b=65, t=90))
fig.show()
```

## 2. Matplotlib

Matplotlib is a versatile library capable of creating static, animated, and interactive visualizations in Python.

### Installation

```bash
pip install matplotlib
```

### Example: Interactive 3D Plot

```python
from mpl_toolkits.mplot3d import Axes3D
import matplotlib.pyplot as plt
import numpy as np

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
X = np.linspace(-5, 5, 100)
Y = np.linspace(-5, 5, 100)
X, Y = np.meshgrid(X, Y)
Z = np.sin(np.sqrt(X**2 + Y**2))

ax.plot_surface(X, Y, Z, cmap='viridis')
plt.show()
```

## 3. Bokeh

Bokeh is a great library for creating interactive plots and dashboards directly in modern web browsers.

### Installation

```bash
pip install bokeh
```

### Example: Interactive Line Chart

```python
from bokeh.plotting import figure, show, output_file

# prepare some data
x = [0.1, 0.5, 1.0, 1.5, 2.0, 2.5, 3.0]
y = [i**2 for i in x]

# output to static HTML file
output_file("lines.html")

# create a new plot with a title and axis labels
p = figure(title="simple line example", x_axis_label='x', y_axis_label='y')

# add a line renderer with legend and line thickness
p.line(x, y, legend_label="Temp.", line_width=2)

show(p)
```

## Conclusion

The examples provided above demonstrate the capabilities of Plotly, Matplotlib, and Bokeh for creating sophisticated interactive and static visualizations in Python. Each library has its strengths, and you can choose one based on your specific needs.
