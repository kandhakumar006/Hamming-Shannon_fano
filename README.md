## Huffman-Shannon_fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

## Aim:
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

## Tools Required:
python IDE with Numpy and Scipy.

## Program:
```
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
## Calculation:
![Image 2025-03-28 at 11 31 03_a290f5d3](https://github.com/user-attachments/assets/ee3d743a-d8c9-4c32-ad3c-875e0d0f64c7)
![Image 2025-03-28 at 11 11 35_f4f43905](https://github.com/user-attachments/assets/34cf2ea1-bd61-4429-a5fc-202dc5e75d90)
![Image 2025-03-28 at 11 11 36_c6ccb1a2](https://github.com/user-attachments/assets/54d5cc8d-72e8-40c2-9e72-b7adc40d4e04)
![Image 2025-03-28 at 11 16 59_35643e5a](https://github.com/user-attachments/assets/6e8ee4f8-7b6b-485c-a321-b062687e530d)


## Results:
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25

Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
