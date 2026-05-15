Optimization Techniques in Deep CNNs 🧠📉

A comparative analysis of optimization algorithms, loss functions, and architectural enhancements (Attention Mechanisms) in Convolutional Neural Networks (CNNs).

This project was developed to explore how different optimization landscapes affect the convergence, stability, and generalization of neural networks using the CIFAR-10 dataset.

🚀 Project Overview

The training of deep neural networks heavily depends on the selection of optimization techniques and loss functions. This repository contains the code and analysis for comparing three distinct CNN structures:

Model 1: The Baseline (Adam Optimizer + Cross-Entropy Loss)

Model 2: The Regularized Network (RMSprop Optimizer + L2 Penalty/Weight Decay)

Model 3: The Attention-Enhanced Network (Adam Optimizer + Mean Squared Error Loss)

Through these models, we explore the trade-offs between convergence speed, the prevention of overfitting via mathematical penalties, and how architectural changes (like Spatial Attention) can overcome sub-optimal loss functions.

🛠️ Tech Stack

Language: Python

Framework: PyTorch, Torchvision

Data Visualization: Matplotlib, NumPy

Environment: Designed for Google Colab (GPU accelerated)

📊 Results & Analysis

Final Training Logs

--- Final Model Evaluation ---
Model_1_Baseline          | Test Accuracy: 72.44%
Model_2_Regularized       | Test Accuracy: 68.04%
Model_3_Attention_MSE     | Test Accuracy: 73.32%


1. Training Dynamics (The Optimization Path)

<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/8ff92fcb-c624-4473-b35b-3d2ac0908173" />


We tracked the training loss over 10 epochs to observe how Adam and RMSprop navigate their respective loss landscapes.

Baseline (Blue): Showed rapid, standard convergence thanks to Adam's momentum.

Regularized (Orange): The L2 penalty mathematically restricted the optimizer, preventing aggressive memorization and resulting in a higher, smoother training loss.

Attention + MSE (Green): Operated on a fundamentally smaller scale (MSE vs. Logarithmic Cross-Entropy), but successfully minimized the error space.

2. Final Generalization (Test Accuracy)

<img width="842" height="444" alt="image" src="https://github.com/user-attachments/assets/7d686a2a-0540-4267-8f04-c1d925bdb34b" />

The ultimate metric of an optimization strategy is its ability to generalize to unseen data.

Winner: The Attention + MSE model achieved the highest accuracy (73.32%). Despite MSE being sub-optimal for classification compared to Cross-Entropy, the Spatial Attention mechanism provided enough representational power to overcome this mathematical handicap.

Runner-Up: Baseline (72.44%).

Underperformed: Regularized Network (68.04%), suggesting the chosen L2 penalty was overly restrictive for a network of this depth, leading to slight underfitting.

3. Explainable AI (XAI) - Spatial Attention

<img width="1159" height="407" alt="image" src="https://github.com/user-attachments/assets/874186be-ab45-490d-a1c0-83c88023aac8" />


To understand why Model 3 performed the best, we extracted the Spatial Attention maps to visualize the optimization focus.

Instead of treating all pixels equally, the network learned to mathematically prioritize the structural contours of the subject (e.g., the body of the cat) while ignoring background noise. This proves the optimizer concentrated its updates on the most visually relevant features.

💻 How to Run

Clone this repository:

git clone [https://github.com/didardagidir/CNN.git](https://github.com/didardagidir/CNN.git)


Open the Jupyter Notebook / Google Colab file.

Ensure GPU runtime is enabled (Runtime > Change runtime type > GPU).

Run the cells sequentially. The CIFAR-10 dataset will be downloaded automatically via torchvision.

📝 License

This project is open-source and available under the MIT License.
