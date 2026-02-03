# 8-Bit-Arithmetic-Operations-using-8085
# NAME: GOKUL PRASAD H
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:
# ADDITION:
### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
```
LDA 4400H 
MOV B, A 
LDA 4401H
ADD B
STA 4300H
JC STORE_CARRY
HLT
STORE_CARRY:MVI A, 01H
STA 4400H
HLT
```

### Output:
<img width="1906" height="1012" alt="Screenshot 2026-02-02 182131" src="https://github.com/user-attachments/assets/008a918e-efc0-4848-a09a-8e02488ddf49" />
<img width="1832" height="900" alt="Screenshot 2026-02-02 185201" src="https://github.com/user-attachments/assets/105f7ebe-31bd-48e2-bb48-a5f73d6857fc" />

# STEPS:

<img width="827" height="1199" alt="Screenshot 2026-02-02 190652" src="https://github.com/user-attachments/assets/c7917909-9b87-4c21-ab08-970c0e9775c7" />

<img width="1047" height="1103" alt="image" src="https://github.com/user-attachments/assets/065e6cab-9884-4282-b32b-6fd1318821fd" />






# SUBTRACTION:
### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
```
LDA 4200H
MOV C,A
LDA 4201H
CMP C 
JC SWAP
SWAP:
MOV B,A
MOV A,C
SUB B
STA 4300H
HLT 
```

### Output:
<img width="1832" height="947" alt="Screenshot 2026-02-02 191531" src="https://github.com/user-attachments/assets/e08bd54f-ad7d-459e-a409-e4a9b766e895" />
<img width="1823" height="946" alt="Screenshot 2026-02-02 191547" src="https://github.com/user-attachments/assets/6e1a0af2-775f-4382-8b38-21000cc53444" />

# STEPS:
<img width="615" height="1280" alt="image" src="https://github.com/user-attachments/assets/8049a322-c7d9-44fa-aada-c31a6a055de1" />
<img width="1280" height="1170" alt="image" src="https://github.com/user-attachments/assets/4fb1fc5e-eab8-4ae8-9401-c1704201c8f3" />



# MULTIPLICATION:
### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
```
LDA 4200H 
MOV C, A
LDA 4201H
MOV B,A
MVI A, 00H
LOOP:ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
```

### Output:
<img width="1835" height="951" alt="Screenshot 2026-02-02 210052" src="https://github.com/user-attachments/assets/19bfd53f-2fb0-4670-b6a3-7431861df069" />
<img width="1825" height="945" alt="Screenshot 2026-02-02 210109" src="https://github.com/user-attachments/assets/fbbb1e0a-2cc3-48fa-9376-21247e92b737" />

# STEPS:
<img width="1040" height="1600" alt="image" src="https://github.com/user-attachments/assets/c6595b65-7753-40cf-b724-6c85136dd481" />
<img width="1600" height="1199" alt="image" src="https://github.com/user-attachments/assets/eeccc418-c997-4bac-bde2-2424146fe829" />



# DIVISION:
### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
```
LDA 4200H 
MOV C,A
LDA 4201H
MOV B, A
MVI A,00H
LOOP:CMP B
JC END
SUB B 
INR A 
JMP LOOP
END: STA 4300H
MOV A,C
STA 4301H
HLT
```

### Output:
<img width="1828" height="938" alt="Screenshot 2026-02-02 210805" src="https://github.com/user-attachments/assets/b6eadc7b-629b-4453-ba7f-1be0182e0387" />

<img width="1820" height="947" alt="Screenshot 2026-02-02 210824" src="https://github.com/user-attachments/assets/67f03569-2d5b-40d3-8a7d-3eef36292f12" />

# STEPS:
<img width="959" height="1280" alt="image" src="https://github.com/user-attachments/assets/540a4592-6cb8-4ef7-bad8-b157efd1a76d" />
<img width="805" height="1280" alt="image" src="https://github.com/user-attachments/assets/f08ba888-3d6b-4064-95db-bdaf43be6be7" />
<img width="1280" height="959" alt="image" src="https://github.com/user-attachments/assets/b5cf2fda-05d8-4eee-aec1-a1ac70368a63" />
<img width="1280" height="609" alt="image" src="https://github.com/user-attachments/assets/5ffd14c2-f28a-4925-8484-18b16c00efef" />




## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

