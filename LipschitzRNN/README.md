# Lipschitz Recurrent Neural Networks

Before running the script, you need to install the `torchdiffeq` package. Use the following command:

```bash
pip install torchdiffeq




Here is an example ro run the Lipschitz RNN on the CIFAR-10 dataset:

```python3 driver.py --name cifar10 --model LipschitzRNN --T 3072 --n_units 32 --epochs 30 --eps 0.03 --lr 0.003 --lr_decay 0.1 --lr_decay_epoch 90 --beta 0.75 --gamma 0.001 --seed 1 ```



Reference
----------
[https://arxiv.org/pdf/2006.12070.pdf](https://arxiv.org/pdf/2006.12070.pdf)
