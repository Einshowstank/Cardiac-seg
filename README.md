# Cardiac MRI Segmentation

![build status](https://travis-ci.org/chuckyee/cardiac-segmentation.svg?branch=master)

This repository contains code and models to identify the right ventricle in
cardiac MRI images. The model we use is dilated u-net.The model is implemented on Keras.

For the problem description, models and results, please see the blog post
[here](https://chuckyee.github.io/cardiac-segmentation/).

## Installation

The main code is written as a Python package named `rvseg_f'. After cloning this
repository to your machine, install with:

```bash
cd cloned/path
pip install .
```

You should then be able to use the package in Python:

```python
import matplotlib.pyplot as plt
from rvseg import patient, models

p = patient.PatientData("RVSC-data/TrainingSet/patient01")
# Explore p.images, p.endocardium_masks, etc.
```

## Running models

Scripts for model training and evaluation are located under /scripts/.

```bash
python -u scripts/train.py defaults.config
```

Note: this package is written with the Tensorflow backend in mind -- (batch,
height, width, channels) ordered is assumed and is not portable to Theano.
