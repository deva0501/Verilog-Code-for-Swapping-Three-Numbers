# Verilog-Code-for-Swapping-Three-Numbers:
Aim:
  To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.

Apparatus Required:
  Vivado 2023.1 or equivalent Verilog simulation tool.

Procedure:

1.Launch Vivado 2023.1:
      Open Vivado and create a new project.
      
2.Write the Verilog Code for Swapping:
    Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
    
3.Create the Testbench:
    Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
    
4.Add the Verilog Files:
    Add the Verilog module and the testbench file to the Vivado project.

5.Run Simulation:
    Run the behavioral simulation in Vivado to verify the swapping operation.

6.Observe the Waveforms:
    Examine the waveform to confirm that the values of the three numbers are swapped as expected.

7.Save and Document Results:
    Capture the waveform output and include the results in your report for verification.

Verilog Code for swapping three numbers:
```verilog
module swaping_three_num(
  input wire [7:0] a_in,
  input wire [7:0] b_in, 
  input wire [7:0] c_in, 
  output reg [7:0] a_out, 
  output reg [7:0] b_out, 
  output reg [7:0] c_out ); 
  always @(*)
   begin
    a_out = b_in; 
    b_out = c_in; 
    c_out = a_in; 
     end
      endmodule
```
simulated output:
    ![WhatsApp Image 2025-04-19 at 14 04 01_7135bf5e](https://github.com/user-attachments/assets/a1b03357-9744-4593-b4bd-dc82652a2d5a)

verilog code in Testbench for Swapping Three Numbers:
```verilog
module swap_three_numbers(
  input wire [7:0] a_in,
  input wire [7:0] b_in, 
  input wire [7:0] c_in, 
  output reg [7:0] a_out, 
  output reg [7:0] b_out, 
  output reg [7:0] c_out ); 
  always @(*)
   begin
    a_out = b_in; 
    b_out = c_in; 
    c_out = a_in; 
     end
      endmodule

module swapping_three_numbers_tb;

// Inputs
reg [7:0] a;
reg [7:0] b;
reg [7:0] c;

// Outputs
wire [7:0] a_out;
wire [7:0] b_out;
wire [7:0] c_out;

// Instantiate the Unit Under Test (UUT)
swap_three_numbers uut (
    .a_in(a),
    .b_in(b),
    .c_in(c),
    .a_out(a_out),
    .b_out(b_out),
    .c_out(c_out)
);

// Test procedure
initial begin
    // Initialize inputs
    a = 8'd10; 
    b = 8'd20; 
    c = 8'd30; 

    #10;

    $display("Before Swap: a = %d, b = %d, c = %d", a, b, c);
    #10;
    $display("After Swap: a = %d, b = %d, c = %d", a_out, b_out, c_out);
    
    #10 $stop;
end
endmodule
```
simulated output:
    ![WhatsApp Image 2025-04-19 at 14 25 39_ec7d08c2](https://github.com/user-attachments/assets/df41f207-20d5-4539-aac4-88b817a0ff1d)

Conclusion:
     In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
