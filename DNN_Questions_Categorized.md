# DNN (Deep Neural Networks) - Comprehensive Exam Questions (Full Verbatim)

**Papers Covered:**
- 2020 EC3 Regular (50% weightage) - July 2020
- 2020 EC3 Makeup (50% weightage) - July 2020
- 2022 EC3 Regular (30 marks)
- 2022 EC3 Makeup (30 marks)
- 2023 EC3 Regular (30 marks)
- 2024 EC3 Regular (35 marks) - Sept 2024
- 2024 EC3 Makeup (35 marks) - Oct 2024

> **Note:** Questions involving diagrams/figures are marked with [DIAGRAM IN ORIGINAL]. Refer to the original PDF for visual content.

---

## 1. CNN - Architecture, Parameters & Computations

### Q1 [2020 Makeup, Q1A - 10M]

Refer to the following code snippet of a CNN implementation using Keras:

```python
from keras.models import Sequential
from keras.layers import Conv2D, MaxPooling2D, Flatten, Dense
classifier = Sequential()
classifier.add(Conv2D(filters=16, kernel_size=(4, 4), strides=(2, 2),
                      input_shape=(32, 32, 3), activation='relu'))
classifier.add(MaxPooling2D(pool_size=(3, 3), strides=(2, 2)))
classifier.add(Conv2D(filters=10, kernel_size=(3, 3), padding='same',
                      activation='relu'))
classifier.add(MaxPooling2D(pool_size=(3, 3), strides=(1, 1)))
classifier.add(Flatten())
classifier.add(Dense(units=64, activation='relu'))
classifier.add(Dense(units=1, activation='sigmoid'))
classifier.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
```

a) Calculate the dimension of the input matrix at each step of the network. [3M]
b) What would be the difference in the dimension of the input vector of the fully connected layer had we not performed convolution steps? [1M]
c) Above code uses "adam" optimizer. What benefit does this over traditional SGD? [2M]
d) You want to train a picture classifier for your face. What is the key data pre-processing step needed and disadvantages? [2M]

B. Which is NOT a pre-processing technique? (i) Stemming/Lemmatization (ii) Lowercase (iii) Removing punctuations/stop words (iv) POS tagging [0.5M]

C. BLEU Score code:
```python
>>> from nltk.translate.bleu_score import corpus_bleu
>>> references = [[['this', 'is', 'not' 'a', 'test'], ['this', 'is', 'a', 'test']]]
>>> hypothesis = [['this', 'is', 'a', 'test']]
>>> score = corpus_bleu(references, hypothesis, weights=(0.3, 0.3, 0.3, 0))
>>> print(score)
```
What will be the output? [0.5M]

---

### Q2 [2023 Regular, Q3 - 8M]

Two historians want to classify images of historical objects into 3 classes: Antiquity (y=0), Middle Ages (y=1), Modern Era (y=2). For each layer, calculate weights, biases, and feature map sizes.

| Layer | Activation map dimensions | Number of weights | Number of biases |
|-------|--------------------------|-------------------|------------------|
| INPUT | 128 x 128 x 3 | 0 | 0 |
| CONV-9-32 | ? | ? | ? |
| POOL-2 | ? | 0 | 0 |
| CONV-5-64 | ? | ? | ? |
| POOL-2 | ? | 0 | 0 |
| CONV-5-64 | ? | ? | ? |
| POOL-2 | ? | 0 | 0 |
| FC-64 | ? | ? | ? |
| FC-3 | ? | ? | ? |

(Padding=0, Stride=1 for Conv; Stride=K, Padding=0 for Pool)

---

### Q3 [2023 Regular, Q5 - 6M]

NiN architecture: one NiN block + global average pooling + softmax. Block: 1x1 conv (20 filters), three 3x3 conv (50 filters each), two 5x5 conv (20 filters each), ReLU after each. Input: 256x256 greyscale.

(a) Parameters in one NiN block. [4M]
(b) Output feature map dimensions after NiN block. [1M]
(c) Total parameters in entire architecture. [1M]

---

### Q4 [2020 Regular, Q1B - 5M]

VGG16 with Batch Normalization:
```python
from tensorflow.keras.applications.vgg16 import VGG16
model = VGG16()
model.layers.pop()
model = Model(inputs=model.inputs, outputs=model.layers[-2].output)
```

a) Total additional trainable parameters (betas and gammas) if BN added after every conv layer? [2.5M]
b) Total non-trainable parameters (means and variances) in first 3 BN layers? [2.5M]

---

### Q5 [2024 Makeup, Q1 - 10M]

```python
dnnModel = models.Sequential()
dnnModel.add(layers.Dense(60, activation='tanh', input_shape=(64*64,)))
dnnModel.add(layers.Dense(40, activation='relu'))
dnnModel.add(layers.Dense(20, activation='relu'))
dnnModel.add(layers.Dense(10, activation='relu'))
dnnModel.add(layers.Dense(4, activation='softmax'))
```

a) Number of hidden layers. [1M]
b) Number of categories classified. [1M]
c) Size of input vector. [1M]
d) Draw the network. [1M]
e) When to use sigmoid vs softmax in output layer? [2M]
f) Compare tanh and ReLU in terms of gradients. [2M]
g) Compare momentum-based GD vs RMSprop. [2M]

---

### Q6 [2024 Makeup, Q4c - 3M]

Fully connected 3-layered feedforward NN: all layers have 5 neurons except output (4 neurons). Draw architecture and show total learnable parameters at each layer.

---

## 2. Convolution Operations (Transposed, Dilated, Stacked, Inception)

### Q1 [2020 Makeup, Q4 - 8M]

A. 2x2 convolution operator O = [[-1,1],[-1,1]]. Stacking two operators:
a) Size of equivalent operator V? [1M]
b) Show elements Vij. [3M]

B. Transposed convolution of kernel [[0,2],[1,3]] with input [[0,2],[1,3]], stride=1, padding=0:
a) Size of result? b) Show result. [2M]

C. Google LeNet inception block. Input: 20x20x500. Output depths: 200, 100, 20, 75.
a) Output volume size? Padding for 1x1, 3x3, 5x5? [1M]
b) Parameters in block? [1M]

---

### Q2 [2020 Regular, Q4 - 10M]

A. 1x3 operator o = [-1, 2, -1]. Stacking two:
a) Size of equivalent O? [1M]
b) Show elements O(i,j). [3M]

B. 3x3 operator on 7x7 input:
```
Operator:        Input (7x7):
-1  0  -1       0.5  1  1  1  1  1  1
 0  4   0       1  0.5  0  0  0  0  0
-1  0  -1       ...
```
a) Output size for 2-dilated convolution, padding=0, stride=1? [1M]
b) Value at (2,1)? [2M]

C. 1x1 conv on 50x50x200 → depth 50, then 5x5 conv → 50x50x75:
a) Padding sizes? [1M]
b) Total multiplication operations? [2M]

---

## 3. RNN - Design & Computation

### Q1 [2020 Makeup, Q5 - 10M]

Design RNN for parity bit (output 1 when #zeros seen is even). Input: binary R-to-L. 1 input, 2 hidden, 1 output. Hard threshold activation.

$h_t = step(Wh_{t-1} + Ux - b_h)$, $y_t = step(vh_t - b_y)$

Example: Input 0,1,0,0,1,0,1 → Output 0,0,1,0,0,1,1

A. State representations for FSM. [1M]
B. Boolean functions for $h_t$ and $y_t$. [4M]
C. Specify U(2x1), v(1x2), W(2x2), $b_h$(2x1), $b_y$. Elements only -1, 1, or 0. [5M]

---

### Q2 [2020 Regular, Q5 - 9M]

Design RNN for binary addition (arbitrary length, LSB first, zero-padded). 2 inputs, 3 hidden, 1 output.

Example: 100111 + 110010 = 1011001
- Input 1: 1,1,1,0,0,1,0
- Input 2: 0,1,0,0,1,1,0
- Output: 1,0,0,1,1,0,1

A. Choose state representations. [1M]
B. Specify U(3x2), v(1x3), W(3x3), $b_h$(3x1), $b_y$. [8M]

---

### Q3 [2023 Regular, Q2 - 6M]

RNN for moving sum of difference: $p=\{0.6,0.4,0.3,1.2,-1.2\}$, $q=\{-1.2,1.2,0.3,0.4,0.6\}$ → output $\{1.8,1.0,1.0,1.8,0\}$. Linear activation.

(a) Minimum hidden nodes? [1M]
(b) Compute W, U, V, $b_h$, $b_y$ (integers only). [5M]

---

### Q4 [2024 Regular, Q2 - 12M]

a) Vanilla RNN computation [8M]: $X=[1,1,0]^T$, $W=[0.2,0.3,0.8]^T$, $U=[0.5,0.6,0.2]^T$, $V=[0.4,0.2,0.1]^T$, biases=0. Compute outputs at each timestep and state after t=3.

b) Ultrasound video report generation [4M]: 36 frames, 360x240 grayscale. Suggest RNN type, depth, LSTM vs GRU vs Bidirectional.

---

### Q5 [2024 Makeup, Q2a - 4M]

```python
Model = Sequential()
Model.add(SimpleRNN(4, input_shape=(4, 6), activation=activation[0]))
Model.add(Dense(1, activation="Sigmoid"))
```
Draw architecture. Calculate parameters: RNN = $W_{xh} + W_{hh} + b_h = 4\times6 + 4\times4 + 4 = 44$. Output = $4\times1 + 1 = 5$. Total = 49.

---

## 4. LSTM - Parameter Calculation

### Q1 [2023 Regular, Q4 - 5M]

LSTM: input_size=210, hidden_size=28, no bidirectional, output=212 vector. Calculate total parameters gate-wise:
- Cell state: $n_i \times n_h + n_h \times n_h + n_h = 210\times28 + 28\times28 + 28$
- Input gate: same
- Forget gate: same
- Output gate: same
- Output projection: $n_h \times n_o + n_o = 28\times212 + 212$

---

### Q2 [2024 Makeup, Q2b - 6M]

LSTM cell: $X_t$=4, $h_t$=5, $C_t$=5.
i) Parameters at forget gate: $W_f = 5 \times [4+5] = 45$, $b_f = 5$, total = 50. [4M]
ii) Can $\sigma$ be replaced with tanh? Justify. [2M]

---

## 5. Attention Mechanisms & Transformers

### Q1 [2023 Regular, Q1 - 5M]

Compute dimensions: $d=2048$, $d_k=512$, $d_v=1024$, $h=4$.
- $W^Q = (h \times d) \times d_k = (4\times2048) \times 512$
- $W^K = (h \times d) \times d_k$
- $W^V = (h \times d) \times d_v$
- Attention vector = $d_v = 4 \times 1024$
- $W^O = h \times d_v \times d = 4 \times 1024 \times 2048$

---

### Q2 [2024 Regular, Q3 - 10M]

a) Self-attention with 3 words (2-d vectors). Given $W_q$, $W_k$, $W_v$ matrices (3x3 each). Show Q, K, V computation, scaled scores, softmax, output. [6M]

b) Types of attention in Transformers (self-attention, masked/cross attention). [2M]

c) Bahdanau attention: justification, disadvantages, alternatives. [2M]

---

### Q3 [2024 Makeup, Q3 - 8M]

$Q_1=[1,0]$, $Q_2=[0,1]$, $K_1=[1,1]$, $K_2=[0,1]$, $V_1=[2,1]$, $V_2=[0,3]$

| | K1 | K2 |
|---|---|---|
| Q1 | $[1,0]\cdot[1,1]=1$ | $[1,0]\cdot[0,1]=0$ |
| Q2 | $[0,1]\cdot[1,1]=1$ | $[0,1]\cdot[0,1]=1$ |

Softmax Q1: $[e/(e+1), 1/(e+1)]$. Softmax Q2: $[0.5, 0.5]$

Output Q1: $[2e/(e+1), (e+3)/(e+1)]$. Output Q2: $[1, 2]$

---

## 6. Optimization (GD, Momentum, Adam)

### Q1 [2020 Makeup, Q3 - 10M]

$$E(w_1, w_2) = 0.05 + \frac{(w_1-3)^2}{4} + \frac{(w_2-4)^2}{9} - \frac{(w_1-3)(w_2-4)}{6}$$

$(w_1,w_2)=(1,1)$ at t-1, $(1.5,2.0)$ at t. $\eta=0.3$, $\beta=0.9$.

a) Minimum of E? [1M]
b) $(w_1,w_2)$ at t+1 using standard GD? [1.5M]
c) Using momentum? [2M]
d) Using Nesterov? [2M]
e) Which gives highest reduction? [0.5M]

Also: What is saddle point? SGD advantage? Batch vs mini-batch GD curves? Learning rate decay?

---

## 7. Backpropagation & Computational Graphs

### Q1 [2020 Regular, Q3 - 9M]

Computational graph for $g(x) = \tanh(x)$. Calculate all partial derivatives. Is randomizing data needed in full-batch GD? When is GD vs SGD preferred?

---

### Q2 [2022 Makeup, Q5 - 5M]

$f = relu(ax + by + c)$. Given $a=3, b=2, c=-5, x=2, y=3$.
Forward: $p=6, q=6, r=12, s=7, f=7$. Compute $\partial f/\partial a$, $\partial f/\partial b$, $\partial f/\partial c$.

---

## 8. Perceptron & MLP

### Q1 [2020 Regular, Q2 - 9M]

Even parity generator for 5-bit string. Step threshold activation.
A. Min hidden nodes (single layer)? [2M]
B. Min hidden nodes (multiple layers)? How many layers? [3M]
C. Total weights (single layer)? [2M]
D. Total weights (multiple layers)? [2M]

---

### Q2 [2020 Makeup, Q2 - 8M]

A. ReLU network with bias T: find output for x=1.0, 2.5, 4, 8. [DIAGRAM IN ORIGINAL]
B. Even parity for (x1,x2): specify w1-w6, b1-b3. Weights only +1,-1,0.

---

### Q3 [2020 Regular, Q1A - 10M]

TensorFlow ANN code (16→8→3, softmax output):
a) Output layer activation? Why softmax? Sigmoid difference? [2M]
b) Compute output: input=[2,0,1,0], weights=[[0.2,0.3,0.2,0.1],[0.1,0.2,0.5,0.1],[0.2,0.1,0.1,0.1]], bias=[0.3,0.1,0.1]. [3M]

---

## 9. Regularization & Overfitting

### Q1 [2024 Regular, Q1b - 4M]

Mr Raju: dropout + batch normalization. Mr Robert: deeper model + early stopping. Assess both approaches for reducing overfitting.

---

## 10. GANs & VAE

### Q1 [2020 Makeup, Q6 - 4M]

[DIAGRAM IN ORIGINAL - Generator cost vs D(G(z))]
A. Early in training, D(G(z)) closer to 0 or 1? Why? [1M]
B. Saturating vs non-saturating cost: which to choose? Why? [1M]
C. Convolution types in CNN-based GANs? [1M]
D. Why KL divergence in VAE? [1M]

---

## 11. Transfer Learning & Applications

### Q1 [2024 Regular, Q4 - 7M]

a) Rare disease from MRI (75% labeled): learning paradigm, architecture, loss function, class imbalance handling. [4M]

b) Weather prediction (7 days→3 days, each day: temp+humidity+wind as 128-d): architecture, parameters (hidden=128), can future affect past? [3M]

---

## 12. Neural Architecture Search

### Q1 [2024 Makeup, Q4a-b - 4M]

a) One-Shot Architecture Search: how it works. [2M]
b) One advantage and one disadvantage for NAS performance estimation. [2M]

---
