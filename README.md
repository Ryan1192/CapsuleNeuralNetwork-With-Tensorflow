# CapsuleNeuralNetwork-With-Tensorflow

[](https://www.google.com/search?q=CONTRIBUTING.md)
[](https://opensource.org/licenses/Apache-2.0)

A Tensorflow implementation of the CapsNet architecture described in Hinton's paper [Dynamic Routing Between Capsules](https://arxiv.org/abs/1710.09829).

> **Current Status:**
>
> 1.  The code is operational but has some deviations from the paper, primarily due to a misunderstanding of the capsule concept, including the routing "for" loop and margin loss (issue \#8, thanks for the reminder—my oversight).
> 2.  Some outcomes from the 'incorrect' version have been shared, though they are not as effective as the results presented in the paper.

---

> **Ongoing Tasks:**
>
> 1.  Revise the routing algorithm code.
> 2.  Fine-tune the margin loss.
> 3.  Enhance the evaluation pipeline.

---

## Prerequisites

- Python
- NumPy
- [Tensorflow](https://github.com/tensorflow/tensorflow) (Currently using version 1.3.0, though other versions might also work)
- tqdm (for displaying training progress information)

---

## Getting Started

### Training Phase

**Step 1.**
Clone this repository using `git`.

```bash
git clone ithub.com/Ryan1192/CapsuleNeuralNetwork-With-Tensorflow
cd CapsuleNeuralNetwork-With-Tensorflow
```

**Step 2.**
Download the [MNIST dataset](http://yann.lecun.com/exdb/mnist/). Move (`mv`) and extract the files into the `data/mnist` directory. (Be cautious of any backslashes that might appear around curly braces if you copy the `wget` command to your terminal; remove them.)

```bash
mkdir -p data/mnist
wget -c -P data/mnist http://yann.lecun.com/exdb/mnist/{train-images-idx3-ubyte.gz,train-labels-idx1-ubyte.gz,t10k-images-idx3-ubyte.gz,t10k-labels-idx1-ubyte.gz}
gunzip data/mnist/*.gz
```

**Step 3.**
Initiate training via the command line:

```bash
pip install tqdm  # Install if not already present
python train.py
```

The `tqdm` package is optional, serving only as a utility for visualizing training progress. If you prefer not to use it, modify the loop `for in step ...` to `for step in range(num_batch)` in the `train.py` script.

---

### Evaluation Phase

```bash
python eval.py --is_training False
```

---

## Outcomes

Results from the 'incorrect' version (addressing Issue \#8):

- Training Loss:

- Test Accuracy:
  | Epoch | 49 | 51 |
  | :----- | :---- | :---- |
  | Test Acc | 94.69% | 94.71% |

---

Results after correcting Issue \#8: (To be updated)

> My brief observations on capsules:
>
> 1.  A novel neural unit type (vector-in, vector-out, rather than scalar-in, scalar-out).
> 2.  The routing algorithm shares similarities with attention mechanisms.
> 3.  Overall, a promising work with significant potential for further exploration.

---

## Future Work:

- Complete the MNIST implementation of CapsNet (Progress: 90%).
- Conduct various experiments with CapsNet:
  - Utilizing different datasets.
  - Modifying the model architecture.
