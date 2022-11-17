# Lab4_IES
3 questions for Lab 4 of IES


Question 1)
Using the WDT timer interrupt process, Toggle your Green LED with a 250msec interval.

The ms interval can be changed by altering the following line
      WDTCTL = WDT_ADLY_250;   
for a interval of 500 the code would be 
      WDTCTL = WDT_ADLY_500;   
      

The output can be changed by altering the following lines 
P6OUT &= ~BIT6;
P6DIR |= BIT6;                                  
P6OUT^=BIT6;

To change the output to be P1.0 it would be 
P1OUT &= ~BIT0;
P1DIR |= BIT0;                                  
P1OUT^=BIT0;
--------------------------------------------------------------------------------


Question 2)
Generate a PWM with a 10% duty cycle and 500ms period using polling process. This targets P6.6
To control the duty cycle the following code can be changed 
TB0CCR0 = 16350 - 1;        // This is the period times 32700 - 1 (32700 is frequency in Hz)
TB0CCR1 = 1635;             //Note this should be 10% of the above value to get a duty of 10%

To see how to alter this code see question 3
--------------------------------------------------------------------------------


Question 3)
Generate a PWM with a 20% duty cycle and 250ms period.
This code is identical to question 2 and 
insted alters the code to produce a different 
duty cycle, period, and frequency

TB0CCR0 = 8175 - 1;
 TB0CCR1 = 1635;     
