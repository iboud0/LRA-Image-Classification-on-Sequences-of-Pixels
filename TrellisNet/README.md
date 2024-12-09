# Trellis Networks

Before running the script, make sure you are in the seq_MNIST_CIFAR folder:

```cd seq_MNIST_CIFAR```




Here is an example ro run the TrellisNet on the CIFAR-10 dataset:

```python seq_mnist_cifar.py --nhid 32 --nlevels 5 --lr 5e-3 --epochs 50 --batch_size 128 --wdecay 1e-4 --optim Adam --cifar```



Reference
----------
[https://arxiv.org/pdf/1810.06682v2](https://arxiv.org/pdf/1810.06682v2)
