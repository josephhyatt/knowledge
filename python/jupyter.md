# Jupyter

* Login to Jupyter through `terminal`

```bash
jupyter notebook
```

* Open Anaconda Navigator

      `bash anaconda-navigator`

* Python Notebook Files are saved as `.ipynb`

## Importing Modules

* `help(module_name)` will list all functions for module
  * Example `help(math)`

```python
## Option 1
    # Imports all commands for module
    import <modual name>
    # Example
    import math
## Option 2
    # Only importing part of a module
    from math import <function name>
    # Example
    from math import sqrt
## Option 3
    # Renaming module from sqrt to s for less typing
    from math import sqrt as <variable name>
    # Example
    from math import sqrt as s
## Option 4
    # Import all features from module (could be problematic)
    # Example
    from math import *
```

## Must-have Packages for Finance and Data Science

```python
import numpy # Third-part package allowing you to work with multidimensional arrays
import pandas # Enhances NumPy by allowing you to organize data in a tabular form and to attach descriptive labels to the rows and the columns of the table
import matplotlib # A 2D plotting library specially designed for visualization of NumPy computations
import math # Mathematical functions
import random # Invokes random number generators
import statsmodels # Descriptive statistics, plotting functions, regressions
import pandas_datareader 
```

