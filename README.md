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

![comp_new_sche](https://user-images.githubusercontent.com/110079790/219589422-3d7d33c4-77ca-4fa0-8cb5-a7c06d9af13f.png)

### comparator testing   


![comp_new1](https://user-images.githubusercontent.com/110079790/219589606-7764b5c0-f718-413b-8216-b98d946054f0.png)    

## Opamp  
![opamp](https://user-images.githubusercontent.com/110079790/219589822-96f518b5-7155-4f64-9b49-016c5fc0e4f2.png)    

## Substractor and residue Amplifier   

![substractor](https://user-images.githubusercontent.com/110079790/220255878-7bafc963-35b6-448f-8607-fa5533c388cc.png)

## substractor and residue amp. testing   


for  Rf = 8k ,rest resistors are of 2k    



![substractor_with_different_r](https://user-images.githubusercontent.com/110079790/220255909-e3648a2d-2724-4553-9422-f5e2fed676dd.png)



## Encoder   

![encoder](https://user-images.githubusercontent.com/110079790/219590743-dcb1ee34-6b06-49ea-b9e9-6c6a4b082c27.png)    



## 2bit_flash adc  

![2bitadc_analog](https://user-images.githubusercontent.com/110079790/219590890-407b4a1b-5f21-491d-8a76-bbbffec40e57.png)

![2bit_graph](https://user-images.githubusercontent.com/110079790/219590965-337d8763-b8fa-4812-b82f-9ab4a9e28acb.png)


with sine input of ac magnitude of 1.4 v     

reference voltage of 2 volt     

and VDD of 1.8 volt     

we are getting B1 B0 =10   

![2bit_2nd](https://user-images.githubusercontent.com/110079790/219591043-6741acab-00aa-4701-bc13-34f0f65cf01d.png)





