# LSTNet

- This repo contains an MXNet implementation of [this](https://arxiv.org/pdf/1703.07015.pdf) state of the art time series forecasting model.

![](./docs/model_architecture.png)

## Running the code

1. Download & extract the training data: 
    - `$ mkdir data && cd data`
    - `$ wget https://github.com/laiguokun/multivariate-time-series-data/raw/master/electricity/electricity.txt.gz`
    - `$ gunzip electricity.txt.gz`
2. Train the model:
    - `$ cd src && python lstnet.py`

## Proof of implementation

- Model in the paper predicts with h = 3 on electricity dataset
- L2 model achieves *RSE = 0.0967, RAE = 0.0581 and CORR = 0.8941* on test data
- My results are *RSE = , RAE =  and CORR =* on validation data

## Hyperparameters...

- q = {2^0, 2^1, ... , 2^9} (1 week is typical value)
- Convolutional num layers  = {50, 100, 200}
- Kernel size = 6
- Recurrent state size = {50, 100, 200}
- Skip recurrent state size = {20, 50, 100}
- p = 24h for electricity dataset
- AR lambda = {0.1,1,10}
- Adam optimizer
- Dropout after every layer =  {0.1, 0.2}


