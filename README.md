📘 Backpropagation From Scratch (Lending Club Risk Model)

This project walks through backpropagation line-by-line using real Lending Club credit-risk data.

No frameworks.
No hidden math.
Just pure linear algebra, calculus, and Python.

If you've ever wanted to truly understand how models learn, this breakdown makes backpropagation “click.”

🔍 What Backpropagation Really Does

Backpropagation answers one question:

“How should I change each weight to make the prediction slightly less wrong?”

It works by combining:

Linear algebra → forward pass

Chain rule of calculus → backward pass

Together, they drive the learning process.

1️⃣ Forward Pass (Linear Algebra)
Linear Score

We start with the dot product:

𝑧
=
𝑤
⋅
𝑥
+
𝑏
z=w⋅x+b

Where:

x ∈ ℝ³ is the scaled borrower feature vector

w ∈ ℝ³ is the weight vector

b is the bias

z is a scalar representing the model’s raw “risk score”

The dot product determines how strongly the input aligns with the learned weights — effectively defining a hyperplane separating “good loan” vs “bad loan.”

Probability (Sigmoid)
𝑝
=
𝜎
(
𝑧
)
p=σ(z)

The sigmoid transforms the linear score into a meaningful probability of default.

Loss (Binary Cross-Entropy)

We measure how wrong the prediction was:

𝐿
=
−
[
𝑦
𝑙
𝑜
𝑔
(
𝑝
)
+
(
1
−
𝑦
)
𝑙
𝑜
𝑔
(
1
−
𝑝
)
]
L=−[ylog(p)+(1−y)log(1−p)]
2️⃣ Backward Pass (Chain Rule of Calculus)

Now we push the error backward through the computation graph.

Step 1 — How loss changes with respect to probability
𝑑
𝐿
/
𝑑
𝑝
dL/dp
Step 2 — How probability changes with respect to the linear score
𝑑
𝑝
/
𝑑
𝑧
=
𝑝
(
1
−
𝑝
)
dp/dz=p(1−p)
Chain Rule — Bringing it all together
𝑑
𝐿
/
𝑑
𝑧
=
(
𝑑
𝐿
/
𝑑
𝑝
)
∗
(
𝑑
𝑝
/
𝑑
𝑧
)
=
𝑝
−
𝑦
dL/dz=(dL/dp)∗(dp/dz)=p−y

This is one of the most elegant results in machine learning:
the derivative of the entire loss collapses to (prediction − truth).

Weight Gradients
𝑑
𝐿
/
𝑑
𝑤
𝑗
=
(
𝑝
−
𝑦
)
𝑥
𝑗
dL/dw
j
	​

=(p−y)x
j
	​


Where:

x_j comes from linear algebra (input vector)

p - y comes from calculus (chain rule)

Every weight update depends on two things:

The model’s error

The feature that contributed to that error

That’s learning.

📉 Running It on a Real Borrower

Using real Lending Club data:

3 scaled financial features

Ground-truth default label (is_bad)

Initial weights and bias

One gradient descent step

After the update:

Loss decreases

Prediction becomes more accurate

The model improves immediately

Backprop is compounding interest for intelligence.

🧠 Why Backprop Matters

Backpropagation powers:

Logistic Regression

Neural Networks

Transformers

LLMs

Recommendation engines

Risk scoring systems

Reinforcement learning

If a model learns, backprop is doing the work.

📓 Notebook Included

The repo contains a full Python notebook that shows:

Manual computation of logits

Sigmoid transformation

Cross-entropy loss

Full derivative chain rule

Weight gradients

Post-update accuracy improvement

Completely transparent — no shortcuts.

💬 Final Thought

Understanding backprop gives you X-ray vision into how AI actually learns.

Once you see it, you can never unsee it.

You don’t just use models —
you engineer them.
