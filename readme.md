
# Monte Carlo Integral Approximation

This project provides a Python implementation of a Monte Carlo method to approximate definite integrals of a given function. The implementation supports visualizing the integral and the random points used in the computation. The package contains two main classes: `MonteCarloIntegral` and `GraphicMonteCarloIntegral`.

---

## Features

1. **Monte Carlo Approximation**:
   - Random sampling to approximate definite integrals.
   - Handles positive and negative parts of the function within the interval.

2. **Validation**:
   - Ensures the function accepts a single argument and returns numerical values.
   - Validates the interval (`a < b`).

3. **Visualization**:
   - Graphical output showing the function, the bounding box, and the random points inside and outside the area under the curve.
   - Adjustable number of points displayed in the plot.

---

## Classes

### 1. `MonteCarloIntegral`

This class performs Monte Carlo integration by:
- Generating random points within a defined bounding box.
- Checking which points fall under the function curve.
- Calculating the approximate integral.

#### Methods:
- `__init__(n, a, b, f)`: Initialize with precision (`10^n` points), bounds (`a`, `b`), and the function (`f`).
- `is_valid_interval()`: Validates the interval.
- `is_valid_function()`: Validates the function signature.
- `set_f_min_max()`: Finds the minimum and maximum values of the function in the interval.
- `set_box_area()`: Calculates the bounding box area.
- `set_random_values()`: Generates random `(x, y)` points.
- `get_inside()`: Determines how many points fall under the curve.
- `result()`: Returns the calculated integral.

---

### 2. `GraphicMonteCarloIntegral`

Extends `MonteCarloIntegral` with graphical visualization capabilities.

#### Additional Methods:
- `separate_points()`: Separates points into "inside" and "outside" groups for plotting.
- `plot()`: Plots the function, the bounding box, and the random points.

---

## Installation

Ensure you have Python 3.7+ and the following libraries installed:
- `numpy`
- `scipy`
- `matplotlib`

To install the dependencies:
```bash
pip install numpy scipy matplotlib
```

---

## Usage

### Example: Approximating an Integral
```python
from montecarlo_integral import MonteCarloIntegral, GraphicMonteCarloIntegral

# Define the function to integrate
def f(x: float) -> float:
    return x**2 - 4

# Create a Monte Carlo integral instance
mc = MonteCarloIntegral(n=6, a=-2, b=2, f=f)
print("Integral:", mc.result())

# Create a graphical Monte Carlo integral instance
gmc = GraphicMonteCarloIntegral(n=5, a=-2, b=2, f=f)
gmc.plot()
```

---

## Example Output
### Console
```
Integral: -5.333
```

### Visualization
A plot displaying:
- The function curve.
- Bounding box around the function's range.
- Random points inside and outside the curve.

---

## Contribution

Feel free to fork this project and submit pull requests for enhancements or bug fixes. Suggestions for additional features are welcome!

---

## License

This project is licensed under the MIT License.

Enjoy exploring the Monte Carlo method with this project! 😊
