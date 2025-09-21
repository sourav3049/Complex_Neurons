
# 📘 Background: Wirtinger Calculus Basics

## 1. Motivation
- Standard **gradient descent** is designed for **real-valued functions**.  
- Many ML problems (signal processing, quantum ML, complex networks) naturally involve **complex variables**.  
- **Wirtinger calculus** provides a clean framework to differentiate complex functions without restricting to holomorphic ones.  

---

## 2. Complex Variables Refresher
- A complex number:  
  \\[
  z = x + i y \\quad (x,y \\in \\mathbb{R})
  \\]  
- Conjugate:  
  \\[
  \\bar{z} = x - i y
  \\]  

Any complex function \\(f(z, \\bar{z})\\) can be expressed in terms of \\(x, y\\).  

---

## 3. Wirtinger Derivatives
Instead of real partials \\(\\partial/\\partial x, \\partial/\\partial y\\), define:  

\\[
\\frac{\\partial}{\\partial z} = \\tfrac{1}{2}\\Big(\\frac{\\partial}{\\partial x} - i \\frac{\\partial}{\\partial y}\\Big), 
\\quad
\\frac{\\partial}{\\partial \\bar{z}} = \\tfrac{1}{2}\\Big(\\frac{\\partial}{\\partial x} + i \\frac{\\partial}{\\partial y}\\Big)
\\]

Key property: treat \\(z\\) and \\(\\bar{z}\\) as **independent variables**.  

---

## 4. Example
Let  
\\[
f(z,\\bar{z}) = z\\bar{z} = |z|^2
\\]  
Then:  
\\[
\\frac{\\partial f}{\\partial z} = \\bar{z}, \\quad \\frac{\\partial f}{\\partial \\bar{z}} = z
\\]  

---

## 5. Why Useful in Gradient Descent
- For **loss functions** \\(L(z,\\bar{z}) \\in \\mathbb{R}\\), update rule can be:  
  \\[
  z \\leftarrow z - \\eta \\frac{\\partial L}{\\partial \\bar{z}}
  \\]  
- This avoids separating into real + imaginary parts explicitly.  
- Enables **complex-valued neural networks** and potentially better **gradient flow**.  

---
