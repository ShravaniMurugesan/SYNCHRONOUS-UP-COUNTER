### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**
```
1.Type the program in Quartus software.
2.Compile and run the program.
3.Generate the RTL schematic and save the logic diagram.
4.Create nodes for inputs and outputs to generate the timing diagram.
5.For different input combinations generate the timing diagram.
```
**PROGRAM**
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
Developed by:shravani.m 
RegisterNumber:24006268
*/
```
```
module exp11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin  
   if(!rstn)
	   out <=0;
	else
     out	<= out+1;
end
endmodule
```
**RTL LOGIC UP COUNTER**

![WhatsApp Image 2024-12-30 at 20 28 40_7957dc91](https://github.com/user-attachments/assets/258de0d0-63fc-4691-ac9d-723036e39ae8)

**TIMING DIAGRAM FOR IP COUNTER**
![WhatsApp Image 2024-12-30 at 20 29 08_2f62e103](https://github.com/user-attachments/assets/d43c4f4c-990d-4127-aaba-c93421f947f2)

**TRUTH TABLE**
![WhatsApp Image 2024-12-30 at 20 30 40_dcabc874](https://github.com/user-attachments/assets/3e560a64-2733-4dfe-b8c6-34a91964d1c7)

**RESULTS**
The synchronous-up-counter are the output is verified.
