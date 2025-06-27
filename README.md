# Data-Driven Dynamic Factor Modeling via Manifold Learning

__A paper that integrates diffusion maps, a nonlinear manifold learning technique, with Kalman filtering within a supervised learning framework to estimate high-dimensional nonlinear observation dynamics and perform response variable prediction while accounting for dynamic correlations, without imposing restrictive parametric assumptions__

The link to our paper draft is [here](https://www.arxiv.org/abs/2506.19945).

Authors: [Agostino Capponi](https://www.columbia.edu/~ac3827/), [Graeme Baker](https://scholar.google.com/citations?user=AC-bMRoAAAAJ&hl=en), [Jose Sidaoui](https://ieor.columbia.edu/content/jose-sidaoui-gali) .

Contact Jose [jas2545@columbia.edu](mailto:jas2545@columbia.edu) or Graeme [gb2847@columbia.edu](mailto:gb2847@columbia.edu) for questions.
## Data
We model the series of stock returns via a classical macroeconomic factor model with the 124 FRED-MD macro-level factors from [McCracken & Ng](https://www.tandfonline.com/doi/full/10.1080/07350015.2015.1086655) plus the 8 macroeconomic factors from [Goyal & Welch](https://academic.oup.com/rfs/article-abstract/21/4/1455/1565737). This gives us a total of D=132 common factors. We utilize the curated data version as provided from [Chen, et. al](https://pubsonline.informs.org/doi/abs/10.1287/mnsc.2023.4695). The monthly stock returns data is obtained from CRSP. The time period considered is 1967-2016. We consider stocks trading in the NYSE, NASDAQ, and the American Stock Exchange.

## Code

The code file _jdkf.ipynb_ is a self-contained Jupyter notebook that implements the version of the diffusion maps algorithm used in our paper (i.e. with the modified Mahalanobis distance and RBF kernel), and the joint diffusion Kalman filter for the linear case. The notebook _benchmarks.ipynb_ implements our benchmark algorithms, namely SSA, Static PCA, and Dynamic PCA. Finally, the notebook _backtesting_algorithm.ipynb_ implements our historical backtesting algorithm with periodic re-fitting of our Kalman filter using the functions defined in _jdkf.ipynb_ and _benchmarks.ipynb_. 

Additionally, we include the notebook _example_3_3.ipynb_ which implements the simulation for eigenfunction and stochastic process recovery from Example 3.3 in our paper. 
