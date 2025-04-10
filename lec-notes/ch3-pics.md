![image-20250313171222780](ch3-pics.assets/image-20250313171222780.png)











![image-20250316222539264](ch3-pics.assets/image-20250316222539264.png)







![image-20250316223046413](ch3-pics.assets/image-20250316223046413.png)











![image-20250316223122736](ch3-pics.assets/image-20250316223122736.png)





![image-20250314233130795](ch3-pics.assets/image-20250314233130795.png)











![draw](ch3-pics.assets/draw.png)



![draw](ch3-pics.assets/draw-2943173.png)

![Screenshot 2025-03-25 at 19.47.55](ch3-pics.assets/Screenshot 2025-03-25 at 19.47.55.png)



```python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# Define the function from R^2 to R
def f(x, y):
    return np.sin(x) * np.cos(y)  # has both positive and negative values

# Generate grid over R^2
x = np.linspace(-3, 3, 100)
y = np.linspace(-3, 3, 100)
X, Y = np.meshgrid(x, y)
Z = f(X, Y)

# Create mask for positive and negative regions
Z_positive = np.where(Z > 0, Z, np.nan)
Z_negative = np.where(Z <= 0, Z, np.nan)

# Plotting
fig = plt.figure(figsize=(10, 8))
ax = fig.add_subplot(111, projection='3d')

# Plot positive surface
ax.plot_surface(X, Y, Z_positive, cmap='Reds', edgecolor='none', alpha=0.8, label='Positive region')

# Plot negative surface
ax.plot_surface(X, Y, Z_negative, cmap='Blues', edgecolor='none', alpha=0.8, label='Negative region')

# Plot the z=0 plane
ax.plot_surface(X, Y, np.zeros_like(Z), color='gray', alpha=0.3)

# Labels
ax.set_title("Visualization of a Signed Function on R^2", fontsize=14)
ax.set_xlabel("x")
ax.set_ylabel("y")
ax.set_zlabel("f(x, y)")

plt.tight_layout()
plt.show()

```

![Screenshot 2025-03-25 at 21.21.13](ch3-pics.assets/singular.png)





![absctn](ch3-pics.assets/absctn.png)





![Screenshot 2025-04-10 at 15.39.23](ch3-pics.assets/Screenshot 2025-04-10 at 15.39.23.png)







![Screenshot 2025-04-10 at 15.39.58](ch3-pics.assets/Screenshot 2025-04-10 at 15.39.58.png)
