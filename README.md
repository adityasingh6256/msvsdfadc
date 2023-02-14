# mixed signal flash ADC   

## abstract   
Flash or parallel converter have the Highest Speed of any Type of ADC.As they use one comaparator per quantization level(2^N-1) and 2^N resistors.The obvious of this Converter is the speed with which one conversion can take place which is Trades High speed with area Counterbalanced by Doubling the area with each bit increased resolution.For example,an 8-bit Converter requires 255 comparators wheras a 9-bit ADC requires 511.Flash converters have traditionally been limited to 6 or 8 bits resolution with the conversion rates of 10-40Ms/s.The disadvantages of flash ADC are the area and power requirements of the 2^N-1 comparators. So,To achive High resolutions with Lower power consumpution Two-step ADCs,pipelined ADCs are introduced to the Flash ADC archietecture.        

## Normal flash ADC   
It is formed of a series of comparators, each one comparing the input signal to a unique reference voltage. The comparator outputs connect to the inputs of a priority encoder circuit, which then produces a binary output. The following illustration shows a 3-bit flash ADC circuit:

![three-bit-flash-ADC-circuit_2](https://user-images.githubusercontent.com/110079790/217727478-d96bb606-066b-4256-9885-c87ad3e39f6f.jpg)

Vref is a stable reference voltage provided by a precision voltage regulator as part of the converter circuit, not shown in the schematic. As the analog input voltage exceeds the reference voltage at each comparator, the comparator outputs will sequentially saturate to a high state. The priority encoder generates a binary number based on the highest-order active input, ignoring all other active inputs.

When operated, the flash ADC produces an output that looks something like this:

![analog-input-digital-output](https://user-images.githubusercontent.com/110079790/217728843-af300135-3b83-4b29-9fac-341f427c6425.jpg)    

## Proposed Two step flash ADC   

![471320_1_En_84_Fig1_HTML](https://user-images.githubusercontent.com/110079790/218645626-87738d95-592e-427e-87e3-603f25d70bd4.png)

## Blocks in two step flash ADC  

### Digital components   

1. DAC    

2. Latch   

3. Decoder and encoder

### Analog components 
1.comparator   
2.subtractor and residue amplifier  

## Comparator    

Low power CMOS charge sharing dynamic latch comparator- it is fastest comparator and we are going to use it in our flash adc.   

#### Schematic of comparator   

![comp1](https://user-images.githubusercontent.com/110079790/218647539-c364ddfc-85d1-482e-b271-d20c8c666fd4.png)    

#### testing of comparator  

  simulated output voltage waveform of this circuit when Vref+ = Vref- = 0.9V and Vin+ = Vin- = 1.8V is a square wave. 
  width of all PMOS is taken Wp=6 um
  width of all NMOS is taken wn= 3 um
  and Lp=Ln = 0.18 um   
  
  ![out+_out-](https://user-images.githubusercontent.com/110079790/218648190-0290dd7e-23c9-4ef2-a922-6454ec7b9847.png)

In this project, 1.8V supply voltage is used for operation and clock period is 10ns. During the process, speed of the comparator is 100MHz. This design can be used where low power, high speed and low propagation delay are the main requirements.   

#### Transiant analysis    

Giving pulse to Vin and 0.9V to Vref and a pulse    

![graph_comparator](https://user-images.githubusercontent.com/110079790/218647300-6c939b16-f9ce-44e9-a818-44c502ed212b.png)    


![graph_comp1](https://user-images.githubusercontent.com/110079790/218647377-eb29df74-2d18-44dc-a824-b2a76236a8ba.png)





