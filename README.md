# Name: Lokhnath.J
# Register number:23004865
# Exp:6 Synchornous counters  up counter and down counter 
### AIM: To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 3 bit counter, which simply means it can count from 0 to 7 and vice versa based upon the direction of counting (up/down).

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle. The Counter will be set to Zero when “reset” input is at logic high. The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down. The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output. The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence. Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1: Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.
 

The Q outputs of each flip-flop will serve as the respective binary bits of the final, three-bit count:

 
 

# Three-bit “Up” Counter
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/de543c01-fb8f-4572-9f59-5d0104c15f8c)




## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/d70c19f1-cdd7-4a8c-9b60-aa973410f184)



3-bit Count Down Counter
### Procedure
1.Create a new project in Quartus2 software .

2.Name the project as uc for upcounter and dc for down counter.

3.Create a new verilog hdl file in the project file.

4.Name the module declare as dc and uc for down counter and upcounter.

5.Within the module declare input and output variables.

6.Create a loop using if-else with condition parameter as reset.

7.End the loop.

8.End the module

### PROGRAM 
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.

Developed by: Lokhnath.J

RegisterNumber:  23004865
*/

 

# UPCOUNTER
```

module upCounters(clk, A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
   A[2]=(((A[0])&(A[1]))^A[2]);
   A[1]=(A[0])^A[1];
   A[0]=A[0]^1;
end
endmodule
```
# DOWN COUNTER
```
module downCounters(clk,A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
   A[2]=(((~A[0])&(~A[1]))^A[2]);
   A[1]=(~A[0])^A[1];
   A[0]=1^A[0];
end 
endmodule

```
### RTL LOGIC UP COUNTER AND DOWN COUNTER 
# UP COUNTER
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/e20cb60c-a65e-4006-878f-5afacff538d8)

# DOWN COUNTER
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/962d59d6-81a4-42ef-ae1c-5aa59e3f75a7)




### TIMING DIGRAMS FOR COUNTER  
# UP COUNTER
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/c1304f09-3a77-40c1-9578-78ac45537849)


# DOWN COUNTER
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/1025ab33-a078-47aa-9017-871e652f34e5)






### TRUTH TABLE 
# UP COUNTER
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/55b26df6-10d2-4d79-a82e-b24a6c413e7a)


# DOWN COUNTER
![image](https://github.com/Lokhnath10/Exp-7-Synchornous-counters-/assets/138969918/6bbc95b7-8696-45ac-88d8-830a95f0700c)









### RESULTS 
Thus , the 3-bit up and down counter is implemented successfully.
