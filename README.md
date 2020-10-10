# 50.002-Computational-Structures-Mini-Hardware-Project

_THIS FOLDER CONTAINING THE "source" and "constrains" FOLDER THAT CONTAINS INSTRUCTIONS FOR FPGA TO TEST THE 8 DIFFERENT CASES FOR ADDER_


> there are 2 modes in fpga- manual and automatic .

**In Manual mode** takes input(a,b, cin) from adder's switch( the 4 way sitch) to get the values of s and cout shown in the inbuilt adder LEDs.
**In automatic mode** input(i.e. value of a,b,cin) is taken from FPGA (the value of a,b,c keeps changing in a specific clk cycle assigned)and
checks if the output of adder(s and cout) is correct according to the input provided.if it is correct ,then LED [2][5] lights up saying 
it is true. If not the LED remains off.
> the FPGA can switch btw manual to auto mode with a switch (io_dip[0][0])('1'-automatic,'0'-manual).
> A button(io_button[0]) is assigned to rest the clk cycle of the condition's fsm.


_HOW DOES THE AUTOMATIC CHECKER WORK?_
> For manipulating the different test cases(eg-a,b,cin-000,001,100,110...) we make use of fsm which for each state has a preasigned value of a,b,c
as well as hav a predefined value of s,cout. The value(a,b,c) when called will be shown in the led(io_led[1][2:0]) as well as sent it as an input
to the adder.The output of adder(i.e. sand cout) is sent to the FPGA as input which then checks if the the adder's output is correct or not by 
comparing it to the predifined value of s and cout.
