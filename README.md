# GenderPredictor 🧠

A simple neural network from scratch (in Python + NumPy) that predicts gender based on weight and height.  
This project was built as a learning exercise to understand forward propagation, backpropagation, and gradient descent **without** using deep learning frameworks like TensorFlow or PyTorch.

---

## 📌 Features
- Implemented a **2 → 2 → 1** feedforward neural network from scratch.
- Uses the **sigmoid** activation function.
- Trains using **Mean Squared Error (MSE)** loss.
- **Feature scaling** for better convergence.
- Simple classification rule:
  - ≥ 0.5 → Female
  - < 0.5 → Male

---

## 📂 Project Structure
```
.
├── gender_predictor.py   # Main training & prediction script
├── README.md             # Project documentation
└── requirements.txt      # Dependencies list
```

---

## 🚀 Installation & Usage

### 1. Clone the repository
```bash
git clone https://github.com/yousifnimah/GenderPredictor.git
cd GenderPredictor
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run training
```bash
jupyter notebook gender_predictor.ipynb
```

---

## 💻 Example Output
```
Epoch  950 | loss: 0.0185
Epoch 1000 | loss: 0.0168

==== Gender Prediction Results ====
👤 Emily
   📏 Height : 160 cm
   ⚖️ Weight : 50 kg
   🎯 Prediction : 0.958 → Female

👤 Frank
   📏 Height : 190 cm
   ⚖️ Weight : 100 kg
   🎯 Prediction : 0.039 → Male
===================================
```

---

## ⚙️ How It Works

1. **Feature Scaling**
   ```python
   x_scaled = (x - mu) / sigma
   ```
   This centers the data around zero and reduces large value effects.

2. **Feedforward**
   - Inputs pass through **hidden layer (2 neurons)**.
   - Output neuron gives probability via sigmoid.

3. **Backpropagation**
   - Manual gradient computation using chain rule.
   - Weight & bias updates via gradient descent.

4. **Prediction**
   ```python
   if output >= 0.5:
       gender = "Female"
   else:
       gender = "Male"
   ```

---

## 🧮 Network Diagram
```
   Weight (kg) ─┐
                │   w1, w2          w5
                ▼    ┌─── Hidden 1 ───┐
   Height (cm) ─┼──► h1               │
                │   w3, w4          w6
                ▼    └─── Hidden 2 ───┘
                           │
                           ▼
                        Output
```

---

## 📜 License
This project is licensed under the **MIT License** – you can freely use, modify, and distribute it.

---

## 🤝 Contributing
Pull requests are welcome!  
Ideas for improvements:
- Add more features (e.g., age, BMI).
- Visualize the decision boundary.
- Save/load trained models.
