## CIFAR Dataset for Tensorflow

It's common to see tutorials using `mnist` dataset provided by Tensorflow.

I'm expecting more.

In this repo, I wrap up code adapt from my cs231n class and `mnist` code in Tensorflow.

So you can write training code as if you're training with Tensorflow `mnist` dataset but in fact using CIFAR dataset

Enjoy!

## Example

```{python}
# just like what you do mnist in tensorflow
from cifar import read_data_sets

cifar = read_data_sets("./data", one_hot=True)

num_epochs = 10
current_epoch = cifar.train.epochs_completed
for epoch in range(num_epochs):
    while current_epoch >= cifar.train.epochs_completed:
        images, labels = cifar.train.next_batch(100)
        # training model here
    print(epoch)
    # print validation error, loss,...etc
```

## Note

- `cifar/cs231n`: most of the code in this directory is copied from the famous computer vision course in Stanford. You can find the course content over [here](http://cs231n.stanford.edu)
