# VLSI-LAB-EXP-5
# SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

# AIM: To simulate and synthesis finite state machine using Xilinx ISE.

# APPARATUS REQUIRED: 
VIVADO 2023.1


# PROCEDURE: 
1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3.Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design
 

# Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


# VERILOG CODE:

module fsm(clk, rst, x, z);
input clk, rst, x;
output z;
reg [2:1] present_state, NEXT_STATE;
parameter S0=2'b00, S1=2'b01, S2=2'b10, S3=2'b11;
always@(x,present_state)
case(present_state)
S0: if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S0;
S1: if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S2;
S2: if(x)
NEXT_STATE=S3;
else
NEXT_STATE=S0;
S3: if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S2;
endcase
always@(negedge rst, posedge clk)
if(rst)
present_state<=S0;
else
present_state<=NEXT_STATE;
assign z=(present_state==S3);
endmodule


# OUTPUT:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/159164885/ee71d2a4-c5c8-4cd9-8496-0cb9a40291b4)


# RESULT:
Thus,the simulation and synthesis of finite state machine by using vivado has been successfully excecuted and verified.


