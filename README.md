# projects
Quantum Computing and Machine Learning Projects
Projects from my senior year Modern Topics in CS course at Taipei American School (2025-2026), plus some other extensions and individual projects.
Covers quantum algorithms in Qiskit, ML built from scratch in NumPy, and deep learning in Keras and PyTorch.

Files
Quantum
grovers_3sat_oracle_qiskit.ipynb
Grover's algorithm applied to a 3-SAT problem. I built the oracle from scratch -- clause ancillas, phase kickback with a Z gate, and a full uncomputation pass to keep it reversible. Also computes the optimal iteration count analytically and plots success probability vs. iterations.
simons_algorithm_gf2_oracle_qiskit.ipynb
Simon's algorithm for an n=4 instance. The oracle encodes f(x) = Ax mod 2 as a CNOT circuit where each 1 in the matrix becomes a CNOT gate. After running the circuit, I solved the resulting system of equations over GF(2) by hand to recover the hidden string.

ML from Scratch (NumPy)
linear_regression_gradient_descent_numpy.ipynb
Linear regression on the UCI Obesity dataset. Implemented gradient descent and the normal equation from scratch, with a numerical gradient check to verify the math. Compared results against scikit-learn.
logistic_regression_from_scratch_numpy.ipynb
Logistic regression on a student pass/fail dataset. Implemented the sigmoid, cross-entropy loss, and gradient descent entirely in NumPy. Also added polynomial features up to degree 5 and looked at how overfitting changes with model complexity.
mnist_backprop_from_scratch_to_cnn_keras.ipynb
Starts with a logistic regression baseline on MNIST, then implements a full neural network with backpropagation in pure NumPy -- forward pass (ReLU, softmax), cross-entropy loss, and gradient updates derived by hand. Then builds up to deeper networks and a CNN in Keras (~99% accuracy).

Deep Learning (Keras / PyTorch)
rnn_lstm_gru_text_and_stock_prediction_keras.ipynb
Compares SimpleRNN, LSTM, and GRU on three tasks: character-level Shakespeare generation, word-level Shakespeare generation, and AAPL stock price prediction. Looks at how training time and loss change across architectures and layer depths.
vae_gan_patch_transformer_image_generation_pytorch.ipynb
Three generative models on MNIST, all in PyTorch:

VAE: encoder outputs mean and log-variance, reparameterization trick samples the latent vector, decoder reconstructs the image. Loss is ELBO (reconstruction + KL divergence).
GAN: generator and discriminator trained adversarially. Observed the discriminator-winning failure mode where generator loss keeps climbing while discriminator loss converges.
PatchGPT: a GPT-style transformer that splits each image into 16 patches and predicts them one at a time using causal masking and multi-head self-attention. Also visualizes the attention weights from the first block.


Stack

Qiskit / Qiskit Aer -- quantum circuits
NumPy -- from-scratch implementations
TensorFlow / Keras -- RNNs, CNNs
PyTorch -- VAE, GAN, transformer
scikit-learn -- baselines and preprocessing
Matplotlib -- visualization
