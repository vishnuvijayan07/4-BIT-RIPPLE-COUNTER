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
module bitripple(
   input  wire clk,      
   input  wire reset_n,  
   output reg  [3:0] q   
);


   always @(negedge clk or negedge reset_n) begin
       if (!reset_n)
           q[0] <= 1'b0;
       else
           q[0] <= ~q[0];
   end


   always @(negedge q[0] or negedge reset_n) begin
       if (!reset_n)
           q[1] <= 1'b0;
       else
           q[1] <= ~q[1];
   end


   always @(negedge q[1] or negedge reset_n) begin
       if (!reset_n)
           q[2] <= 1'b0;
       else
           q[2] <= ~q[2];
   end


   always @(negedge q[2] or negedge reset_n) begin
       if (!reset_n)
           q[3] <= 1'b0;
       else
           q[3] <= ~q[3];
   end

endmodule
```

**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1077" height="598" alt="Screenshot 2026-05-28 183006" src="https://github.com/user-attachments/assets/991e39f2-0df2-48bc-aebb-b156052c5c46" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1067" height="590" alt="Screenshot 2026-05-28 183031" src="https://github.com/user-attachments/assets/667e0cbf-e6a4-4a81-ae9d-c53052b396dd" />

**RESULTS**
