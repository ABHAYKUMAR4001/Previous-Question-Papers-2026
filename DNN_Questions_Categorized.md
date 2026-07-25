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

## 1. CNN (Convolutional Neural Networks) - Architecture, Parameters & Computations


### Q1 [2020 Makeup, Q1A - 10M]

Refer to the following code snippet of a CNN implementation using Keras and answer below questions:

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

b) What would be the difference in the dimension of the input vector of the fully connected layer had we not performed convolution steps in this architecture? [1M]

c) Above code uses "adam" optimizer. What benefit does this optimization algorithm have over traditional stochastic gradient descent? [2M]

d) You want to train a picture classifier that identifies your face on the above architecture and therefore you source pictures of yourself from various sources. What is the key data pre-processing step that you will need for the above code to work on your dataset and why? What are the disadvantages of that pre-processing step? [2M]

B. Which one of the following is not a pre-processing technique? [0.5M]
- i. Stemming and Lemmatization
- ii. Converting to lowercase
- iii. Removing punctuations and stop words
- iv. Parts of speech tagging

C. Refer to the following code snippet:
```python
>>> from nltk.translate.bleu_score import corpus_bleu
>>> corpus_bleu(actual, predicted, weights=(0.25, 0.25, 0.25, 0.25))
```

a) In the above code, what does the parameter "weights" signify? [0.5M]
- i. Weights for unigrams only
- ii. Weights for bigrams only
- iii. Weights for 4-grams only
- iv. None of the above

```python
>>> from nltk.translate.bleu_score import corpus_bleu
>>> references = [[['this', 'is', 'not' 'a', 'test'], ['this', 'is', 'a', 'test']]]
>>> hypothesis = [['this', 'is', 'a', 'test']]
>>> score = corpus_bleu(references, hypothesis, weights=(0.3, 0.3, 0.3, 0))
>>> print(score)
```

b) What will be the output of the above code snippet? [0.5M]
- i. 0
- ii. 0.75
- iii. 0.83
- iv. 1.0

---


### Q2 [2020 Regular, Q1 - 10M]

A. Refer to the partial code of an ANN implementation using Tensorflow and answer following questions:

```python
import tensorflow as tf
data = pd.read_csv('train.csv')
a = tf.placeholder(tf.float32, shape=[None, 16])
b = tf.placeholder(tf.float32, shape=[None, 3])
phi = {
    'alpha': tf.Variable(tf.random_normal([16, 8])),
    'beta': tf.Variable(tf.random_normal([8, 3]))
}
omega = {
    'alpha': tf.Variable(tf.random_normal([8])),
    'beta': tf.Variable(tf.random_normal([3]))
}

tl = tf.add(tf.matmul(x, phi['alpha']), omega['alpha'])
tl = tf.nn.relu(tl)
fl = tf.matmul(tl, phi['beta']) + omega['beta'])
cost = tf.reduce_mean(tf.nn.softmax_cross_entropy_with_logits(fl, b))
optimizer = tf.train.AdamOptimizer(learning_rate=0.5).minimize(cost)
init = tf.initialize_all_variables()
```

a) Which activation function is used in the output layer? Why do you think this particular activation function was chosen? What difference would it make if we used sigmoid function instead? [2M]

b) Calculate the output values assuming the input vector to the output layer to be [2,0,1,0], weight matrix to be [[0.2,0.3,0.2,0.1],[0.1,0.2,0.5,0.1],[0.2,0.1,0.1,0.1]] and bias vector to be [0.3,0.1,0.1]. [3M]

B. Refer to the following code snippet:
```python
>>> from tensorflow.keras.applications.vgg16 import VGG16
>>> from tensorflow.keras.models import Model
>>> model = VGG16()
>>> model.layers.pop()
>>> model = Model(inputs=model.inputs, outputs=model.layers[-2].output)
```

a) If we add Batch Normalization after every convolution layer in the modified VGG16 model (popping last layer), what will be the total number of additional trainable parameters, beta's and gamma's? [2.5M]

b) What will be the total number of non-trainable parameters, i.e., means and variances in the first 3 Batch Normalization layers? [2.5M]

---


### Q3 [2023 Regular, Q3 - 8M]

Two historians approach you for your deep learning expertise. They want to classify images of historical objects into 3 classes depending on the time they were created: Antiquity (y = 0), Middle Ages (y = 1) and Modern Era (y = 2).

You come up with a CNN classifier. For each layer, calculate the number of weights, number of biases and the size of the associated feature maps.

The notation follows the convention:
- CONV-K-N denotes a convolutional layer with N filters, each of size KxK. Padding and stride parameters are always 0 and 1 respectively.
- POOL-K indicates a KxK pooling layer with stride K and padding 0.
- FC-N stands for a fully-connected layer with N neurons.

| Layer | Activation map dimensions | Number of weights | Number of biases |
|-------|--------------------------|-------------------|------------------|
| INPUT | 128 x 128 x 3 | 0 | 0 |
| CONV-9-32 | ? | ? | ? |
| POOL-2 | ? | ? | ? |
| CONV-5-64 | ? | ? | ? |
| POOL-2 | ? | ? | ? |
| CONV-5-64 | ? | ? | ? |
| POOL-2 | ? | ? | ? |
| FC-64 | ? | ? | ? |
| FC-3 | ? | ? | ? |

---

### Q4 [2023 Regular, Q5 - 6M]

Consider a simplified version of the NiN architecture with one NiN block followed by global average pooling and a softmax output layer. Each NiN block consists of the following layers:
- 1x1 convolutional layer with 20 filters
- Three separate 3x3 convolutional layers, each with 50 filters
- Two separate 5x5 convolutional layers with 20 filters
- ReLU activation function applied after each convolutional layer

Assume that the input to the NiN architecture is a greyscale image with dimensions of 256x256 pixels. Calculate the following:

(a) The number of parameters (weights and biases) in one NiN block. [4M]

(b) The dimensions of the output feature map after the NiN block. [1M]

(c) The total number of parameters in the entire NiN architecture. [1M]

---


### Q5 [2024 Makeup, Q1 - 10M]

The following code snippet is used for a classification problem:

```python
dnnModel = models.Sequential()
dnnModel.add(layers.Dense(60, activation='tanh', input_shape=(64*64,)))
dnnModel.add(layers.Dense(40, activation='relu'))
dnnModel.add(layers.Dense(20, activation='relu'))
dnnModel.add(layers.Dense(10, activation='relu'))
dnnModel.add(layers.Dense(4, activation='softmax'))
```

a. Find the number of hidden layers. [1M]

b. Find the number of categories that are being classified. [1M]

c. Compute the size of input vector. [1M]

d. Draw the network given by the code snippet. [1M]

e. When will you use a sigmoid against a softmax activation function in the output layer of a DNN. [2M]

f. Compare tanh and ReLU activation functions in terms of gradients. [2M]

g. Compare momentum based gradient descent algorithm against RMSprop. [2M]

---

### Q6 [2024 Makeup, Q4c - 3M]

Consider a fully connected 3 layered feed forward neural network in which all the layers (except output layer) contain 5 neurons and each output layer contains 4 neurons. Draw the architecture of the above mentioned. And show the total number of learnable parameters at each layer and also of the network.

---

## 2. Convolution Operations (Transposed, Dilated, Stacked, Inception)


### Q1 [2020 Makeup, Q4 - 8M]

Answer A. OR B. Answer C.

A. Consider a 2x2 convolution (as per Deep Learning terminology) operator O:

```
-1   1
-1   1
```

Output is generated by stacking two such operators on the 2-D input data (i.e., the operator is applied twice on the input).

a) What is the size of the equivalent operator V that will give the same output, when applied only once on the input data? [1M]

b) Show the elements Vij of equivalent operator V. [3M]

B. a) Assuming stride = 1 and padding = 0 what is the size of transposed convolution of the following 2x2 kernel O with the following input I? [2M]

Kernel O:
```
0  2
1  3
```

Input I:
```
0  2
1  3
```

b) Show the result of the transposed convolution.

C. Consider the following configuration of a sample Google LeNet inception block. Appropriate padding is assumed. The output depth of the 1x1 convolution blocks are, respectively, 200, 100, 20 and 75, as shown in the figure. [DIAGRAM IN ORIGINAL]

Input: 20x20x500

a) What is the size of the output volume? What is the size of padding used during 1x1, 3x3 and 5x5 convolution operations? [1M]

b) How many parameters are there in this block? [1M]

---

### Q2 [2020 Regular, Q4 - 10M]

A. Consider a 1x3 convolution (as per Deep Learning terminology) operator o = [o1, o2, o3] = [-1, 2, -1]. Output is generated by stacking two such operators on the 1-D input data (i.e., the operator is applied twice on the input).

a) What is the size of the equivalent operator O that will give the same output, when applied only once on the input data? [1M]

b) Show the elements O(i,j) of equivalent operator O. [3M]

B. Consider a 3x3 operator and a 7x7 input, as shown below. Point (i, j) corresponds to the i-th row from top to bottom and j-th column from left to right.

3x3 Operator:
```
-1   0  -1
 0   4   0
-1   0  -1
```

7x7 Input:
```
0.5  1  1  1  1  1  1
1  0.5  0  0  0  0  0
0  0.5  1  1  1  1  1
1  0.5  0  0  0  0  0
0  0.5  1  1  1  1  1
1  0.5  0  0  0  0  0
0  0.5  1  1  1  1  1  0.5
```

a) What will be the output size for 2-dilated convolution with padding 0 and stride 1? [1M]

b) What will be the value at (2, 1) in the output plane? [2M]

C. In the following figure, 1x1 operators are used first to process the same 50x50 images of depth 200, and first output 50x50 images of depth 50, and then 5x5 operators are used to output 50x50 images of depth 75. [DIAGRAM IN ORIGINAL]

a) What is the padding size used in the first step and padding size in the last step? [1M]

b) How many multiplication operations are needed here? [2M]

---

## 3. RNN (Recurrent Neural Networks) - Design & Computation


### Q1 [2020 Makeup, Q5 - 10M]

Design a recurrent neural network that outputs a parity bit for binary sequences of arbitrary length. The inputs are given as binary sequences from right to left and output of 1 is generated when number of '0's in the string seen so far is even. For instance, the input string 1010010 would generate an output as follows:

- Input: 0, 1, 0, 0, 1, 0, 1
- Correct output: 0, 0, 1, 0, 0, 1, 1

There is one input unit corresponding to the input bit, and one output unit. The RNN has one input unit x, two hidden units h, and one output unit y. All of the units use the hard threshold activation function, i.e., output is 1 if total weighted input is >= bias, else 0.

Note, at time t: $h_t = step(Wh_{t-1} + Ux - b_h)$ and $y_t = step(vh_t - b_y)$

[DIAGRAM IN ORIGINAL]

A. Specify the state representations for the underlying finite state machine in terms of outputs of 2 hidden nodes. [1M]

B. For the chosen representation, express the current hidden states $h_t$ as Boolean functions of past hidden states $h_{t-1}$ and current input x. Express the current output $y_t$ as a Boolean function of current hidden states $h_t$. [4M]

C. For the obtained Boolean functions, specify weight matrices U (size 2x1), v (size 1x2), and W (size 2x2), bias vector $b_h$ (2x1) and scalar bias $b_y$. Elements of U, v and W can be only -1, 1 or 0. [5M]

---

### Q2 [2020 Regular, Q5 - 9M]

Design a recurrent neural network that adds binary numbers of arbitrary length. The inputs are given as binary sequences, starting with the least significant binary digit. The sequences will be padded with at least one zero on the end. For instance, the problem 100111 + 110010 = 1011001 would be represented as:

- Input 1: 1, 1, 1, 0, 0, 1, 0
- Input 2: 0, 1, 0, 0, 1, 1, 0
- Correct output: 1, 0, 0, 1, 1, 0, 1

There are two input units corresponding to the two inputs, and one output unit. The RNN has two input units x, three hidden units h, and one output unit y. All of the units use the hard threshold activation function, i.e., output is 1 if total weighted input is >= bias, else 0.

Note, at time t: $h_t = step(Wh_{t-1} + Ux + b_h)$ and $y_t = step(vh_t + b_y)$

[DIAGRAM IN ORIGINAL]

A. Choose the state representations for the underlying finite state machine in terms of outputs of 3 hidden nodes. [1M]

B. For the chosen representations, specify weight matrices U (size 3x2), v (size 1x3), and W (size 3x3), bias vector $b_h$ (3x1) and scalar bias $b_y$. Elements of U, v and W can be only -1, 1 or 0. [1+1+1+3+2+1M]

---

### Q3 [2023 Regular, Q2 - 6M]

Design a single hidden layer recurrent neural network that outputs the moving sum of difference of two input real sequences.

For example, left-to-right input sequences $p = \{0.6, 0.4, 0.3, 1.2, -1.2\}$ and $q = \{-1.2, 1.2, 0.3, 0.4, 0.6\}$ will produce the left-to-right output sequence $\{1.8, 1.0, 1.0, 1.8, 0\}$.

All nodes use linear activation function g(x), i.e., g(x) = x. There are two input units corresponding to two input sequences and one output unit. Hidden states are denoted by h.

Note, at time t: $h_t = g(Wh_{t-1} + Ux - b_h)$ and $y_t = g(vh_t - b_y)$

[DIAGRAM IN ORIGINAL]

(a) What is the minimum number of hidden nodes required? Justify. [1M]

(b) Compute W, U, V, $b_h$ and $b_y$. Only integer values are allowed. Show all computations. [5M]

---


### Q4 [2024 Regular, Q2 - 8M + 4M]

a) Compute the outputs in each timestep and the state after timestep = 3 for the Vanilla RNN given below. Assume the biases as zeros. [8M]

$X = [1, 1, 0]^T$
$W = [0.2, 0.3, 0.8]^T$
$U = [0.5, 0.6, 0.2]^T$
$V = [0.4, 0.2, 0.1]^T$

[DIAGRAM IN ORIGINAL - showing RNN unrolled across 3 timesteps]

b) A company is trying to automate generating reports from videos of ultrasound scans. The videos of a beating heart of fetus at a particular section or slice. The report to be generated describes the heart condition and its location and any abnormalities detected. The videos are of 36 frames each. Each frame is 360 x 240 grayscale image. [4M]

a) Suggest suitable type of RNN to be used for this application and justify your selection.
b) Compute the depth of the RNN suggested.
c) Should an LSTM or GRU or Bidirectional RNN be used for this application. Justify your choice.

---

### Q5 [2024 Makeup, Q2a - 4M]

Consider the following code snippet and draw the corresponding architecture. And also calculate number of parameters.

```python
Model = Sequential()
Model.add(SimpleRNN(4, input_shape=(4, 6), activation=activation[0]))
Model.add(Dense(1, activation="Sigmoid"))
```

---

## 4. LSTM & GRU - Parameter Calculation

### Q1 [2023 Regular, Q4 - 5M]

A deep learning researcher is designing an LSTM-based neural network for a natural language processing task. The researcher plans to use a single-layer LSTM with specific architectural parameters. The LSTM layer is expected to have an input size of 210 and a hidden size of 28. Additionally, the researcher decides not to use bidirectionality in the LSTM layer. The expected output is a 212 vector. Based on these specifications, calculate the total number of parameters required for this LSTM layer. Show Gate wise necessary calculations.

- Parameters for cell state = $n_i \times n_h + n_h \times n_h + n_h$
- Parameters for input gate = $n_i \times n_h + n_h \times n_h + n_h$
- Parameters for forget gate = $n_i \times n_h + n_h \times n_h + n_h$
- Parameters for output gate = $n_i \times n_h + n_h \times n_h + n_h$
- Parameters for output projection = $n_h \times n_o + n_o$

---

### Q2 [2024 Makeup, Q2b - 4M + 2M]

Consider the below architecture. [DIAGRAM IN ORIGINAL - LSTM cell diagram with gates]

i) If $X_t$, $h_t$, $C_t$ are of the dimensions 4, 5 and 5 respectively, then find the number of parameters to be trained at $f_t$ (forget gate). Show the calculations/justifications. [4M]

ii) Justify the following statement: "In the above architecture '$\sigma$' can be replaced with 'tanh' to obtain the optimal architecture" [2M]

---

## 5. Attention Mechanisms & Transformers


### Q1 [2023 Regular, Q1 - 5M]

Compute the dimensions of $W^Q$, $W^K$, $W^V$, $W^O$ if the input dimensions and attention dimensions are given as $d = 2048$ and the query and key dimensions are $d_k = 512$ and value dimensions are $d_v = 1024$ and the number of head $h = 4$. Compute the dimensions of the attention vector.

---

### Q2 [2024 Regular, Q3 - 6M + 2M + 2M]

a) Consider a text sequence with 3 words: $\langle w_1, w_2, w_3 \rangle$ such that each word is represented by a 2-d vector as given in matrix X. Show step by step calculations for computing the scaled dot-product based self attention scores using the $W_q$, $W_k$ and $W_v$ matrices given below: [6M]

$$W_q = \begin{bmatrix} 2 & 0 & 2 \\ 2 & 0 & 0 \\ 2 & 1 & 2 \end{bmatrix}$$

$$W_k = \begin{bmatrix} 2 & 2 & 2 \\ 0 & 2 & 1 \\ 0 & 1 & 1 \end{bmatrix}$$

$$W_v = \begin{bmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

b) i) Mention and justify the different types of attention mechanisms used in Transformer architecture. [2M]

ii) Justify the selection of Bahdanau attention and disadvantages due to this selection. Is there any alternative to this attention? [2M]

---

### Q3 [2024 Makeup, Q3 - 8M]

Given a set of query vectors $[Q_1, Q_2]$, key vectors $[K_1, K_2]$ and value vectors $[V_1, V_2]$ where:

$Q_1 = [1, 0]$, $Q_2 = [0, 1]$
$K_1 = [1, 1]$, $K_2 = [0, 1]$
$V_1 = [2, 1]$, $V_2 = [0, 3]$

Calculate the attention scores and attention-weighted outputs for both queries using dot-product attention and softmax.

Step 1: Compute Attention Scores (dot product between Q and K) [4M]
Step 2: Apply Softmax to normalize scores [2M]
Step 3: Calculate Attention-Weighted Output (weighted sum of V vectors) [2M]

---

## 6. Optimization (Gradient Descent, Momentum, Adam, Learning Rate)

### Q1 [2020 Makeup, Q3 - 10M]

A. What is a saddle point? What is the advantage/disadvantage of using Stochastic Gradient Descent in dealing with saddle points? [1M]

B. Figure below shows how the cost decreases (as the number of iterations increases) when two different optimization algorithms are used for training. Which of the graphs corresponds to using batch gradient descent as the optimization algorithm and which one corresponds to using mini-batch gradient descent? Explain. [1M]

[DIAGRAM IN ORIGINAL - Two cost vs iteration curves: (a) smooth, (b) noisy]

C. Figure below shows how the cost decreases (as the number of iterations increases) during training. What could have caused the sudden drop in the cost? Explain. [1M]

[DIAGRAM IN ORIGINAL - Cost curve with sudden drop]

D. Consider an error function:

$$E(w_1, w_2) = 0.05 + \frac{(w_1 - 3)^2}{4} + \frac{(w_2 - 4)^2}{9} - \frac{(w_1 - 3)(w_2 - 4)}{6}$$

Different variants of gradient descent algorithm can be used to minimize this error function w.r.t. $w_1$, $w_2$. Assume $(w_1, w_2) = (1, 1)$ at time (t-1) and after update $(w_1, w_2) = (1.5, 2.0)$ at time t. Assume learning rate $\eta = 0.3$ and momentum update rate $\beta = 0.9$.

a. What is the value of $(w_1, w_2)$ that minimizes this error function? What is the minimum possible value of E? [1M]

b. What is the value of $(w_1, w_2)$ at time (t+1) if standard gradient descent is used? [1.5M]

c. What is the value of $(w_1, w_2)$ at time (t+1) if momentum based gradient descent is used? [2M]

d. What is the value of $(w_1, w_2)$ at time (t+1) if Nesterov's accelerated gradient is used? [2M]

e. Which among the above techniques results in highest reduction in E in this example? [0.5M]

---


### Q2 [2020 Regular, Q3 - 9M]

A. Refer to the computational graph below. The values of the variables in forward pass is indicated in black. Calculate the partial derivatives in the backward pass $\partial g/\partial e$, $\partial g/\partial f$, $\partial g/\partial c$, $\partial g/\partial d$, $\partial g/\partial a$, $\partial g/\partial b$ and $\partial g/\partial x$. [0.5+0.5+1+1+1+1+1+1.5+1.5M]

You can use $d/dx(1/x) = -1/x^2$, $d/dx \exp(x) = \exp(x)$.

[Note: $g(x) = \tanh(x)$]

[DIAGRAM IN ORIGINAL - Computational graph showing forward pass values]

B. Is it necessary to randomize the order of training data in full batch gradient descent? Explain your answer. [1M]

C. When is Gradient Descent preferred over Stochastic Gradient Descent, and vice-versa? Explain your answer. [1M]

---

## 7. Perceptron & MLP (Multi-Layer Perceptron)

### Q1 [2020 Makeup, Q2 - 8M]

A. The hidden nodes in the network below uses ReLU activation functions with bias T, i.e., output = input - T if input >= T, else output is 0. The output node uses a linear activation function, i.e., output = input. For the specified weight configuration, find the output for: [0.5+1+1+1.5M]

[DIAGRAM IN ORIGINAL - Network with multiple hidden nodes with different thresholds T=0,2,3,5,6]

a. x = 1.0
b. x = 2.5
c. x = 4
d. x = 8

B. The following network outputs a Y='1' when number of 1's in input binary string (x1, x2) of length 2 is either zero or even. For odd number of 1's in the input string, output is 0. Specify the weights w1, w2, w3, w4, w5, w6 and bias b1, b2, b3 in the following network. The weights w's can be only +1 or -1 or 0. The nodes use step threshold, i.e., output = 1 if input >= bias, else 0. [3M]

[DIAGRAM IN ORIGINAL - 2-layer network with x1, x2 inputs]

---

### Q2 [2020 Regular, Q2 - 9M]

An even parity bit generator outputs 1 if number of '1's in a binary string is zero or even (otherwise, 0 output is generated). Consider an even parity bit generator for binary string length of 5. Activation functions are step threshold, i.e., output = 1 if total input >= threshold, else 0.

A. What is the minimum number of hidden nodes in a single hidden layer perceptron network required for implementing this even parity generator? [2M]

B. What is the minimum number of hidden nodes if multiple hidden layers are used? How many hidden layers will be required? [3M]

C. What is the total number of weights needed for single hidden layer based implementation? [2M]

D. What is the total number of weights needed for more than one hidden layer based implementation? [2M]

---

## 8. Regularization & Overfitting

### Q1 [2024 Regular, Q1b - 4M]

Two friends Mr Raju and Mr Robert, while experimenting with a deep neural network, found that their model is over-fitting the given training data. The friends referred to the available literature and materials and came up with a solution to reduce the over-fitting.

Mr Raju decided to add 1 dropout along with batch normalization to his model.

Whereas Mr Robert decided to go with a deeper model, hence he added more layers. But he found that his model is struggling to train because of his hardware limitations. So he decided to employ early stopping.

Assess whether the decisions Mr Raju and Mr Robert are taking helps them to proceed in the right direction. [4M]

---

## 9. GANs (Generative Adversarial Networks) & VAE

### Q1 [2020 Makeup, Q6 - 4M]

Consider the following graph representing the training procedure of a generative adversarial network. Cost function of the generator is plotted against the output of the discriminator, given a generated image G(z). The discriminator's output is 0 implies that the discriminator thinks the input has been generated by G (1 if it thinks the input is actually real data).

[DIAGRAM IN ORIGINAL - Generator cost vs D(G(z)) showing saturating and non-saturating cost curves]

A. Early in the training, is the value of D(G(z)) closer to 0 or closer to 1? Why? [1M]

B. Two cost functions are presented in the above figure, which one would you choose to train your network? Why? [1M]

C. What types of convolution are used in the pooling layers of CNN based GANs? [1M]

D. Why is KL divergence used for regularization in variational autoencoders? [1M]

---

## 10. Transfer Learning & DNN Applications


### Q1 [2024 Regular, Q4 - 7M]

a) A medical doctor has approached you to help her identify a rare disease from MRI images. The doctor provides you with a lot of MRI images and 75% of them have the region of interest (lesion) marked with bounding boxes by a radiologist. [4M]

- Choose the most suitable type of learning paradigm and justify your selection.
- Suggest a suitable DNN architecture and justify.
- Suggest a suitable loss function.
- How would you handle the class imbalance?

b) An agency wants to predict weather for the next 3 days based on the past 7 days data. Each day the weather data has temperature, humidity, wind speed and each of which are encoded by 128-dimensional encoding. [3M]

- Draw the architecture / suggest the DNN and compute the number of parameters. (Assume hidden size as 128)
- Can future weather prediction affect past weather conditions? Justify.

---

## 11. Neural Architecture Search (NAS)

### Q1 [2024 Makeup, Q4a-b - 4M]

a. Briefly explain how the method One-Shot Architecture Search works. [2M]

b. Discuss ONE potential advantage and ONE potential disadvantage of using this method for performance estimation in NAS. [2M]

---

## 12. Attention Score Computation (Detailed Numerical)

### Q1 [2024 Regular, Q3 - Full Computation - 6M]

Consider a text sequence with 3 words: <w1, w2, w3> such that each word is represented by a 2-d vector as given in matrix X. Show step by step calculations for computing the scaled dot-product based self attention scores using the Wq, Wk and Wv matrices.

Required steps:
1. Compute Q = X × Wq
2. Compute K = X × Wk
3. Compute V = X × Wv
4. Compute Attention Scores = $\frac{QK^T}{\sqrt{d_k}}$
5. Apply Softmax
6. Compute Output = Softmax(Scores) × V

---

### Q2 [2024 Makeup, Q3 - Full Computation - 8M]

Given:
- $Q_1 = [1, 0]$, $Q_2 = [0, 1]$
- $K_1 = [1, 1]$, $K_2 = [0, 1]$
- $V_1 = [2, 1]$, $V_2 = [0, 3]$

**Step 1: Compute Attention Scores** [4M]

| | K1 | K2 |
|---|---|---|
| Q1 | $Q_1 \cdot K_1 = [1,0] \cdot [1,1] = 1$ | $Q_1 \cdot K_2 = [1,0] \cdot [0,1] = 0$ |
| Q2 | $Q_2 \cdot K_1 = [0,1] \cdot [1,1] = 1$ | $Q_2 \cdot K_2 = [0,1] \cdot [0,1] = 1$ |

**Step 2: Apply Softmax** [2M]

For $Q_1$: $\text{Softmax} = \left[\frac{e^1}{e^1 + e^0}, \frac{e^0}{e^1 + e^0}\right] = \left[\frac{e}{e+1}, \frac{1}{e+1}\right]$

For $Q_2$: $\text{Softmax} = \left[\frac{e^1}{e^1 + e^1}, \frac{e^1}{e^1 + e^1}\right] = [0.5, 0.5]$

**Step 3: Attention-Weighted Output** [2M]

$\text{Output}_{Q_1} = \frac{e}{e+1} \cdot [2,1] + \frac{1}{e+1} \cdot [0,3] = \left[\frac{2e}{e+1}, \frac{e+3}{e+1}\right]$

$\text{Output}_{Q_2} = 0.5 \cdot [2,1] + 0.5 \cdot [0,3] = [1, 2]$

---

## 13. Backpropagation & Computational Graphs

### Q1 [2022 Makeup, Q5 - 5M]

Draw the computational graph for the equation $f = relu(ax + by + c)$. Show the computations of derivatives of f wrt a, b, c in the graph. Using the graph, compute the value of f and the derivatives if $a = 3$, $b = 2$, $c = (-5)$, $x = 2$ and $y = 3$.

Forward pass:
- $p = ax = 6$
- $q = by = 6$
- $r = p + q = 12$
- $s = r + c = 7$
- $f = relu(s) = 7$

Backward pass: Compute $\frac{\partial f}{\partial a}$, $\frac{\partial f}{\partial b}$, $\frac{\partial f}{\partial c}$

---
