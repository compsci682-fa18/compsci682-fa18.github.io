---
layout: page
mathjax: true
permalink: /assignments/assignments2016/assignment2/
---

In this assignment you will practice writing backpropagation code, and training
Neural Networks and Convolutional Neural Networks. The goals of this assignment
are as follows:

- understand **Neural Networks** and how they are arranged in layered
  architectures
- understand and be able to implement (vectorized) **backpropagation**
- implement various **update rules** used to optimize Neural Networks
- implement **batch normalization** for training deep networks
- implement **dropout** to regularize networks
- effectively **cross-validate** and find the best hyperparameters for Neural
  Network architecture
- understand the architecture of **Convolutional Neural Networks** and train
  gain experience with training these models on data

### Setup
Get the code as a zip file [here](http://vis-www.cs.umass.edu/682/asgns/assignment2.zip). As for the dependencies:

**[Option 1] Use Anaconda:**
The preferred approach for installing all the assignment dependencies is to use [Anaconda](https://www.continuum.io/downloads), which is a Python distribution that includes many of the most popular Python packages for science, math, engineering and data analysis. Once you install it you can skip all mentions of requirements and you're ready to go directly to working on the assignment.

**[Option 2] Manual install, virtual environment:**
If you'd like to (instead of Anaconda) go with a more manual and risky installation route you will likely want to create a [virtual environment](http://docs.python-guide.org/en/latest/dev/virtualenvs/) for the project. If you choose not to use a virtual environment, it is up to you to make sure that all dependencies for the code are installed globally on your machine. To set up a virtual environment, run the following:

```bash
cd assignment2
sudo pip install virtualenv      # This may already be installed
virtualenv .env                  # Create a virtual environment
source .env/bin/activate         # Activate the virtual environment
pip install -r requirements.txt  # Install dependencies
# Work on the assignment for a while ...
deactivate                       # Exit the virtual environment
```

**Download data:**
Once you have the starter code, you will need to download the CIFAR-10 dataset.
Run the following from the `assignment2` directory:

```bash
cd datasets
./get_datasets.sh
```

**Compile the Cython extension:** 
Convolutional Neural Networks require a very
efficient implementation. We have implemented of the functionality using
[Cython](http://cython.org/); you will need to compile the Cython extension
before you can run the code. From the `assignment2/asgn2` directory, run the following
command:

```bash
python setup.py build_ext --inplace
```

**Start Jupyter Notebook:**
After you have the CIFAR-10 data, you should start the Jupyter Notebook server from the
`assignment2` directory. If you are unfamiliar with Jupyter, you should read our
[Jupyter tutorial](/notes/jupyter-tutorial/).

**NOTE:** If you are working in a virtual environment on OSX, you may encounter
errors with matplotlib due to the [issues described here](http://matplotlib.org/faq/virtualenv_faq.html). You can work around this issue by starting the Jupyter server using the `start_jupyter_osx.sh` script from the `assignment2` directory; the script assumes that your virtual environment is named `.env`.

### Submitting your work

To make sure everything is working properly, **remember to do a clean run ("Kernel -> Restart & Run All") after you finish work for each notebook** and submit the final version with all the outputs. 
Once you are done working, zip all the code and notebooks in a single file and upload it to Moodle. On Linux or macOS you can run the provided `collectSubmission.sh` script from `assignment2/` to produce a file `assignment2.zip`.

### Q1: Fully-connected Neural Network (30 points)
The Jupyter notebook `FullyConnectedNets.ipynb` will introduce you to our
modular layer design, and then use those layers to implement fully-connected
networks of arbitrary depth. To optimize these models you will implement several
popular update rules.

### Q2: Batch Normalization (30 points)
In the Jupyter notebook `BatchNormalization.ipynb` you will implement batch
normalization, and use it to train deep fully-connected networks.

### Q3: Dropout (10 points)
The Jupyter notebook `Dropout.ipynb` will help you implement Dropout and explore
its effects on model generalization.

### Q4: ConvNet on CIFAR-10 (30 points)
In the Jupyter Notebook `ConvolutionalNetworks.ipynb` you will implement several
new layers that are commonly used in convolutional networks. You will train a
(shallow) convolutional network on CIFAR-10, and it will then be up to you to
train the best network that you can.

### Q5: Do something extra! (up to +10 points)
In the process of training your network, you should feel free to implement
anything that you want to get better performance. You can modify the solver,
implement additional layers, use different types of regularization, use an
ensemble of models, or anything else that comes to mind. If you implement these
or other ideas not covered in the assignment then you will be awarded some bonus
points.

