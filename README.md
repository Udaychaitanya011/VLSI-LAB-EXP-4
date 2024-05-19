EXP-4

DATE:

             SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

**AIM:**
To simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters using Vivado 2023.2

**APPARATUS REQUIRED:**

vivado 2023

# PROCEDURE:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.


LOGIC DIAGRAM

 SR FLIPFLOP:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

 VERILOG CODE:
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

 Output:
![331348058-45243aaa-d907-493d-a13f-7443b3bfa287](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/16a32bed-775f-417f-91ca-ca2c0f1da109)


 JK FLIPFLOP:
![301743103-1510e030-4ddc-42b1-88ce-d00f6f0dc7e6](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/f6fa9fa4-b660-4279-b978-24525b5d83ce)



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

 Output:
![331347927-3312233d-9ae6-4787-b002-fc064731b50f](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/6d707bda-b2d0-49e7-833f-3ab3f1832452)


 T FLIPFLOP:
![331347949-5f40064f-7491-4a52-90a0-6762ce891f55](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/255aaef9-0684-4a13-aa81-adfdc5c60d68)



 VERILOG CODE:

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

 Output:
![331347837-6ded158f-9696-4b37-b460-c8e9222e601d](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/3e17bf86-5eea-4ec0-9557-d51b5d9ef2d5)


 D FLIPFLOP:
![331347828-92d1bacc-e9e8-40ea-a324-25a474eb0e91](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/91eb1f6d-fffc-4075-b5e0-c2bb7a6a0305)


 VERILOG CODE:

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

 Output:
![331347700-2bd11870-e55b-43a9-be17-3df61daf2478](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/a2b8c99e-966e-4173-a878-9d2cca30b631)


 COUNTER:
![331347653-b4cf50df-a052-4d6d-9bb2-b9aebd771584](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/3e30f700-9182-47be-b2de-d26c8a87c6e3)


4bit UPDOWN COUNTER

![331347432-fef31a1b-f55e-4b01-b857-81e635687992](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/06f349b3-3fb1-4257-ab73-eb048f1970bb)


 VERILOG CODE:

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

Output:
![331346909-93f41368-dfbc-486f-8a47-525af2a5511e](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/5480fedc-52d2-486b-998b-8c8daab4b900)


 MOD 10 COUNER:
 
![331346889-d18df4cb-a444-41f4-8a5c-8aa247c14e3e](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/e7e98869-0f96-45c8-a8d8-58f891c4010e)


VERILOG CODE:

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

 Output:

![331346592-df84bdbe-05a1-4a4d-952f-c4e3ac83c89a](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/197ecc0f-4449-4e01-b9f4-bfe02974ece7)

RIPPLE CARRY COUNTER:

![331346533-e1858e63-5bc4-4d6b-974e-e251d82154d2](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/236c62ed-8c17-43e8-863f-82938eaf836e)

VERILOG CODE

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

Output:
![331346337-b6fde017-8c0f-4f03-847a-149c86d518e7](https://github.com/Udaychaitanya011/VLSI-LAB-EXP-4/assets/161430397/7fe8e184-42af-4f11-9dae-5d14350cce6d)


 RESULT:

Thus simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters was succesfully executed and verified.
