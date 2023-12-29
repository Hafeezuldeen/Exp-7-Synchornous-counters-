# NAME: S.HAFEEZUL DEEN
# REFERENCE NO. :23008281 
# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 
### PROCEDURE
```
1.Create a new project in Quartus2 software . 
2.Name the project as uc for upcounter and dc for down counter.
3.Create a new verilog hdl file in the project file.
4.Name the module declare as dc and uc for down counter and upcounter. 
5.Within the module declare input and output variables.
6.Create a loop using if-else with condition parameter as reset.
7.End the loop. 
8.End the module
```
# UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)
### PROGRAM:
```
module up_counter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end 
endmodule
```
### RTL LOGIC FOR UP COUNTER
![293053998-42e688c9-0f09-4855-aa94-999ef57fbd7c](https://github.com/Hafeezuldeen/Exp-7-Synchornous-counters-/assets/144979314/a03a9147-4071-4d8c-b1bb-c94baaacfe25)



### TRUTH TABLE
![293053425-61101a6c-3bc6-4673-8f28-a6cc96261e20](https://github.com/Hafeezuldeen/Exp-7-Synchornous-counters-/assets/144979314/0fad4afb-aff2-4a62-8494-e081757ba1ca)




### TIMING DIAGRAM FOR UP COUNTER
![293053302-503e5497-1348-4cfe-8cb9-f85522c71464](https://github.com/Hafeezuldeen/Exp-7-Synchornous-counters-/assets/144979314/1fa2cb7e-3c27-4c4e-a7be-71bfbca01bb6)





## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
4-bit Count Down CounteTr
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)

### PROGRAM 
```
module COUNTER(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=((~q2)&(~q1))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule
```






### RTL LOGIC DOWN COUNTER 
![293052592-86302d1a-9941-44f5-b0c5-b4a4d197801c](https://github.com/Hafeezuldeen/Exp-7-Synchornous-counters-/assets/144979314/aea0bb57-ab87-4549-9720-c26f35609f2d)





### TRUTH TABLE 
![293052864-f1f16bd2-e699-431f-b573-37a9d7058932](https://github.com/Hafeezuldeen/Exp-7-Synchornous-counters-/assets/144979314/e6ff8e0f-9248-4fa0-b05f-cbe39e102dcf)



### TIMING DIAGRAM FOR DOWN COUNTER
![293052816-2eebdbcf-f101-471e-a1b2-24a7d524a12f](https://github.com/Hafeezuldeen/Exp-7-Synchornous-counters-/assets/144979314/169f6ffa-5e86-4212-9451-25c5981e77b0)








# RESULTS:
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
