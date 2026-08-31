# ECE-2112-PA-2

**Made by: Zechariah Sampang | 2ECE-C**

The content of this repository contains the Programming Assignment 2 for our course "Advanced Computer Programming and Algorithms" this S.Y. 2026-2027. This project covers three Python problems pertaining to Experiment 2: Numerical Python (NumPy).

# **A. Reproducible Normalization Problem**

Create a reproducible random $5 \times 5$ integer ndarray named X using a fixed seed of 2112 and random integers ranging from 10 to 100. Normalize the complete array using the standard score formula:

$Z = \frac{X - \bar{x}}{\sigma}$ where $\bar{x}$ is the mean.

The main Python implementation for this problem is as follows:

```python
import numpy as np

np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

mean = X.mean()
std = np.std(X)

X_normalized = (X - X.mean()) / std

np.save("X_normalized.npy", X_normalized)
```

# **B. Cubes Divisible by 4 Problem**

Create a $10 \times 10$ ndarray named $C$ containing the cubed values of the first 100 positive integers, then apply a Boolean condition on $C$ to extract all elements that satisfy the divisibility condition and store the filtered values in `div_by_4` (preserving row-major order) and export the result as `div_by_4.npy`[cite: 1].

### Methods and Functions Used
- `np.arange(1, 101)` - Generates a 1D array of integers from 1 through 100
- `integers**3` - Uses the exponentiation operator `**` to compute element-wise cubes ($x^3$)
- `.reshape(10, 10)` - Reshapes the 100-element 1D array into a $10 \times 10$ two-dimensional matrix.
- `C[C % 4 == 0]` - Uses Boolean indexing with the modulo operator `%` to select elements where the remainder is 0 when divided by 4 (Divisible by 4).
- `np.save("div_by_4.npy", div_by_4)` - Saves the resulting filtered array as a binary `.npy` file.

### Implementation
```python
import numpy as np

integers = np.arange(1, 101)
cubed_integers = integers**3
C = cubed_integers.reshape(10, 10)

div_by_4 = C[C % 4 == 0]

np.save("div_by_4.npy", div_by_4)
```
# **C. Above-Mean Squares Problem**

Create a $6 \times 6$ ndarray named $S$ containing the squares of the first 36 positive integers ($x \in [1, 36]$) in increasing row-major order, then
Compute the mean of all elements ($\bar{S}$), then use Boolean filtering to select elements strictly greater than the mean. Store these selected values in `above_mean` and export the result as `above_mean.npy`.

### Methods and Functions Used
- `np.arange(1, 37)` - Generates a 1D array of integers from 1 through 36[cite: 2].
- `bintegers**2` - Computes the element-wise square ($x^2$) of each integer[cite: 1, 2].
- `np.reshape(S, (6, 6))` - Reshapes the 36-element array into a $6 \times 6$ matrix[cite: 1, 2].
- `S.mean()` - Calculates the arithmetic mean ($\bar{S}$) across all 36 elements of $S$[cite: 1, 2].
- `S[S > S_mean]` - Uses Boolean indexing to select values strictly greater than `S_mean` ($S > \bar{S}$)[cite: 1, 2].
- `np.save("above_mean.npy", above_mean)` - Exports the array of selected elements into an `.npy` file[cite: 1, 2].

### Implementation
```python
import numpy as np

bintegers = np.arange(1, 37)
S = bintegers**2
S = np.reshape(S, (6, 6))

S_mean = S.mean()
above_mean = S[S > S_mean]

np.save("above_mean.npy", above_mean)
```
Thank you for reading! 

To see the main python program for Programming Assignment 1, click this [link](https://github.com/imwithiu/ECE2112-SAMPANG-PA2/blob/main/ECE_2112-PA2.ipynb) and download. Open on Jupyter Notebook, then run all cells.
