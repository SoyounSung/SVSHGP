Stochastic variational heteroscedastic Gaussian process
====

This is the implementation of the scalable heteroscedastic GP (HGP) developed in "*[Haitao Liu,  Yew-Soon Ong, and Jianfei Cai, Large-scale Heteroscedastic Regression via Gaussian Process](https://arxiv.org/abs/1811.01179).*" Please see the paper for further details.

We here focus on the heteroscedastic Gaussian process regression $y = f + \mathcal{N}(0, \exp(g))$ which integrates the latent function and the noise together in a unified non-parametric Bayesian framework. Though showing flexible and powerful performance, HGP suffers from the cubic time complexity, which strictly limits its application to big data. 

To improve the scalability of HGP,  we introduce inducing variables and perform variational inference to derive an analytical evidence lower bound (ELBO), the part of which factorizes over data points, thus supporting stochastic variational inference for handling large-scale heteroscedastic regression.

The model is implemented based on [GPflow](https://github.com/GPflow/GPflow). To use it, one can

1. download GPflow package from [here](https://github.com/GPflow/GPflow);
2. use  `likelihoods.py` to replace the same file `./gpflow/likelihoods.py` in GPflow; 
3. move `svhgp.py`  to  the folder `./gpflow/models/`;
4. install GPflow through `python setup.py install`.


We have tested the model using GPflow 1.3.0.


* Python 3.7.12 
* numpy 1.19.5
* Tensorflow 1.15.0
* GPflow 1.3.0

$ conda create -n <ENV_NAME> python==3.7.12 
$ conda activate <ENV_NAME>
$ conda uninstall numpy    # if numpy is already installed
$ conda install numpy==1.19.5
$ conda install tensorflow==1.15.0
$ pip install gpflow==1.3.0


after install gpflow copy the folder gpflow to the ~<ENV_NAME>/lib/python3.7/site-packages



The illustration example is provided in

```
demo_SVHGP_1D.ipynb
demo_SVHGP_2D.ipynb
```

<div style="text-align:center">
<img src="https://github.com/0LYS0/SVSHGP/blob/master/result/result.gif">
</div>


