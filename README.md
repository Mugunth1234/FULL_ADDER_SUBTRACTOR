# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**
![Screenshot 2025-03-31 220537](https://github.com/user-attachments/assets/0842c3f1-857d-407b-aa8c-7761318b6397)
![Screenshot 2025-03-31 220544](https://github.com/user-attachments/assets/a1762a72-7d60-477d-bd50-ae5a3e9b3678)



**Procedure**

Write the detailed procedure here

**Program:**
```
Full Adder

  module half (A, B, Cin, Sum, Carry); 
  input A, B, Cin;
  output Sum, Carry;

  wire AxorB, AB, BCin, ACin;

  xor (AxorB, A, B);           
  xor (Sum, AxorB, Cin);       

  and (AB, A, B);              
  and (BCin, B, Cin);          
  and (ACin, A, Cin);          
  or (Carry, AB, BCin, ACin);  
  endmodule

Full Subtractor

 
 module full (A, B, Bin, Diff, Borrow);
 input A, B, Bin;
 output Diff, Borrow;

 wire AxorB, A_not, A_not_and_B, A_not_and_Bin, B_and_Bin;

 xor (AxorB, A, B);               
 xor (Diff, AxorB, Bin);          

 not (A_not, A);                
 and (A_not_and_B, A_not, B);     
 and (A_not_and_Bin, A_not, Bin); 
 and (B_and_Bin, B, Bin);         
 or (Borrow, A_not_and_B, A_not_and_Bin, B_and_Bin); 
 endmodule
````

**RTL Schematic**
![Screenshot 2025-03-31 215556](https://github.com/user-attachments/assets/ba686477-ec1a-4169-bb01-dd2d95b7e663)
![Screenshot 2025-03-31 220134](https://github.com/user-attachments/assets/7f077ddc-b899-4c08-b19d-53e7f6badf17)



**Output Timing Waveform**
![Screenshot 2025-03-31 215845](https://github.com/user-attachments/assets/b050b2fe-dfa2-4195-b0d8-f07d563ff978)
![Screenshot 2025-03-31 220329](https://github.com/user-attachments/assets/743840e4-a65d-4ad8-a31f-40ea9bdd4dc7)



**Result:**



Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



