# VLSI-LAB-EXP-4
SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

# AIM: 
 To simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters using Vivado 2023.2
# APPARATUS REQUIRED:
vivado 2023

# PROCEDURE:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

**LOGIC DIAGRAM**

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

# VERILOG CODE:

module SR(clk,s,r,rst,q );

input s,r,clk,rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({s,r})

2'b00: q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=1'bx;

endcase

end

end

Endmodule

# Output:

![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/f3075dc9-4be7-437f-97b0-b941e5cbe5cd)


JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

VERILOG CODE:
module jk(j,k,clk,rst,Q);

input j,k,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)Q=0;

else

begin

case({j,k})

2'b00:Q=Q;

2'b01:Q=0;

2'b10:Q=1;

2'b11:Q=~Q;

endcase

end

end

Endmodule

# Output:

![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/02c72dc3-644f-4796-a793-b207486cb72f)

# T FLIPFLOP:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)

# VERILOG CODE:

module tff(t,clk,rst,Q);

input t,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else if(t==0)

Q=Q;

else

Q=~Q;

end

Endmodule

# Output:

![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/fcf3ad61-c802-408c-a4af-b00ed844ef83)


# D FLIPFLOP:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)

# VERILOG CODE:

module dff(d,clk,rst,Q);

input d,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else

Q=d;

end

Endmodule

# Output:

![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/deadf610-3722-4e54-921f-bb42f1e3661f)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)

# VERILOG CODE:

module updown(clk,rst,updown,out);

input clk,rst,updown;

output reg[3:0]out;

always@(posedge clk)

begin

if(rst==1)

out=4'b0000;

else if(updown==1);

out=out-1;

end

endmodule

# Output:
![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/3db41447-7cbf-4ba3-8452-697066379ed0

# MOD 10 COUNER:
![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/9cdc72ef-56e2-4ff7-af71-ebf2667f4fea)

# VERILOG CODE:

module mod(clk,rst,out);

input clk,rst;

output reg[3:0]out;

always @(posedge clk)

begin

if(rst==1 | out==4'b1001)

out=4'b0000;

else

out=out+1;

end

endmodule

# Output:
![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/956eacd0-341f-4289-883c-19c7fdf1cfe7)

# RIPPLE CARRY COUNTER:
![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/aa02fa1b-23a6-4651-a15e-38ac1420c577)

# VERILOG CODE

module ripple_carry_counter(q, clk, reset);

output [3:0] q;

input clk, reset;

T_FF tff0(q[0], clk, reset);

T_FF tff1(q[1], q[0], reset);

T_FF tff2(q[2], q[1], reset);

T_FF tff3(q[3], q[2], reset);

endmodule

module T_FF(q, clk, reset);

output q;

input clk, reset;

wire d;

D_FF dff0(q, d, clk, reset);

not n1(d, q);

endmodule

module D_FF(q, d, clk, reset);

output q;

input d, clk, reset;

reg q;

always @(posedge reset or negedge clk)

if (reset)

q = 1'b0;

else

q = d;

endmodule

# Output:
![image](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/614b7c4a-7c17-4118-acf8-997258fabbd6)

# RESULT:
Thus simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters was succesfully executed and verified.









  

