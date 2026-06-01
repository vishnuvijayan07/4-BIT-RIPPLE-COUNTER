# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

**PROGRAM**

```
Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

Developed by: vishnu.v
RegisterNumber: 212225040494
```
```
module log7(clk, rst, t, A, B, C, D); 
input clk, rst, t; 
output A, B, C, D;

wire A, B, C, D;

// Ripple connection
T_flipflop T0 (.q(D), .clk(clk), .rst(rst), .t(t)); 
T_flipflop T1 (.q(C), .clk(D),   .rst(rst), .t(t)); 
T_flipflop T2 (.q(B), .clk(C),   .rst(rst), .t(t)); 
T_flipflop T3 (.q(A), .clk(B),   .rst(rst), .t(t)); 

endmodule 


module T_flipflop(q, clk, rst, t); 
input clk, rst, t; 
output reg q; 

always @(posedge clk) 
begin 
    if (!rst)
        q <= 0;
    else
        q <= (t ? ~q : q);
end

endmodule 
```
**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1919" height="1022" alt="Screenshot 2026-03-17 113136" src="https://github.com/user-attachments/assets/df14e58d-6516-44f6-9599-05f832ea8c47" />


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1919" height="1027" alt="Screenshot 2026-03-17 113717" src="https://github.com/user-attachments/assets/40324680-8816-499e-9d4e-cec09bc1f331" />

**RESULTS**
 Thus implementing 4 Bit Ripple Counter using Verilog and validating their functionality using their functional tables is done successfully.
