# mixed signal  2 STEP flash ADC   

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


![comparator_new_sche](https://user-images.githubusercontent.com/110079790/220752213-9238008a-1cc5-4e82-ae70-d0dd0639d32a.png)     


### comparator testing   


![comptest_schematic](https://user-images.githubusercontent.com/110079790/220752281-9dd7e193-aea8-42af-a248-5231d334a29a.png)    


![new_comp_outgraph](https://user-images.githubusercontent.com/110079790/220752323-cee9fbe0-77cf-412b-9554-45c739d41692.png)

   

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

  ![2BIT_FLASH_adc](https://user-images.githubusercontent.com/110079790/220751798-604c8fc8-5c1e-4cf5-88e3-2402960bba88.png)    


## Testing 2_bit_flash_ADC  


![2bit_flash_adc_test_sche](https://user-images.githubusercontent.com/110079790/220750614-a49e7515-d083-4ebf-8427-42684c09cfd2.png)     

### With DC inputs   

![2bit_flash_graph](https://user-images.githubusercontent.com/110079790/220751442-a54a6498-a5d1-4a0d-ae71-75d15017d417.png)   


### With Sine wave input    

![2bit_flash_sin_vin](https://user-images.githubusercontent.com/110079790/220751542-7b5e93e4-0848-4bb3-a46b-31e07634629c.png)    

## DAC  

### 1_Bit_DAC    

![1bit_dac](https://user-images.githubusercontent.com/110079790/220752537-a1ed79fd-118f-4bc2-a98e-4597716652fa.png)    

### Testing 1bit dac    

![dac_1bit_test](https://user-images.githubusercontent.com/110079790/220752790-1467e2bf-6b43-4b3b-8cfe-6e334d18113f.png)


### 2_Bit_DAC    

![2bit_dac](https://user-images.githubusercontent.com/110079790/220752667-a886d1a0-abdb-411b-a337-aed2c173cea6.png)


# 2 step flash ADC    

### SCHEMATIC    

![2step_flash_adc_sche](https://user-images.githubusercontent.com/110079790/220753216-2ab48acb-19bb-4a8f-8ee3-6e1806361abc.png)

## Two Step FLASH ADC Performance Parameters      

| Parameter| Description| Min | Type | Max | Unit | Condition |
| :---:  | :-: | :-: | :-: | :---:  | :-: | :-: |
|VDDA|Analog supply voltage||3.0||V|T=40 to 85C|
|VDDD|Digital supply voltage||1.8||V|T=40 to 85C|
|VREFH|Reference voltage High|||2.3|V|T=40 to 85C|
|VREFL|Reference voltage LOW|||0|V|T=40 to 85C|
|CLOCK|PULSE |10K||0.5M|V|T=40 to 85C|
|RES|Resolution| |4||bit|for all typical value T=27C|
|R1,R2|analog input Resistances use in substractor and in comparator input||2.1||k ohm|T=-40 to 85C|
|Rf|analog input Resistances use in substractor| |8||k ohm|T=-40 to 85C|
|Rout|analog output Resistances use in comparator| |10||M ohm|T=-40 to 85C|
|C|capacitance for DAC| |40|80|f F|T=-40 to 85C|
|IDDA|analog Current supply| |60||u A|T=27C|




