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

Procedure

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**
```

module up_counter (out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
	if(!rst)
		out<=0;
	else 
		out <= out+1;
end
endmodule
```
```
module down_counter (out,clk,rst);

input clk,rst; 

output reg [3:0]out;

always @ (posedge clk)

begin

if(!rst)

out<=4'b1111;

else 

out <= out-1;

end

endmodule
```


Developed by: Amal Tony Charles A RegisterNumber: 25016419

**RTL LOGIC UP COUNTER**
UP COUNTER
<img width="1467" height="786" alt="Screenshot 2025-12-17 185002" src="https://github.com/user-attachments/assets/b6a277f2-f398-4a2c-aa3c-e1e6945b59d4" />
DOWN COUNTER 
<img width="1276" height="695" alt="Screenshot 2025-12-17 205633" src="https://github.com/user-attachments/assets/50b3623e-fc07-46cb-a5c4-cc0ce1be7afc" />




**TIMING DIAGRAM FOR IP COUNTER
UP COUNTER
<img width="1920" height="1080" alt="Screenshot 2025-12-17 185242" src="https://github.com/user-attachments/assets/b9033c1c-d5ad-486a-9fc0-3fc6d79144b5" />
DOWN COUNTER 
<img width="1920" height="1080" alt="Screenshot 2025-12-17 205825" src="https://github.com/user-attachments/assets/26c7a01b-bc49-4e5f-851b-9d73547a5e49" />



**TRUTH TABLE**
![WhatsApp Image 2025-12-17 at 8 25 10 PM](https://github.com/user-attachments/assets/900af1f0-6cfb-42d7-b158-24ea8903f446)



**RESULTS**
Thus the truth table and logic diagrama for the synchronuous up and synchronous down are verified using quartus program
