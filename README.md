# mixed signal flash ADC   

## abstract   
Flash or parallel converter have the Highest Speed of any Type of ADC.As they use one comaparator per quantization level(2^N-1) and 2^N resistors.The obvious of this Converter is the speed with which one conversion can take place which is Trades High speed with area Counterbalanced by Doubling the area with each bit increased resolution.For example,an 8-bit Converter requires 255 comparators wheras a 9-bit ADC requires 511.Flash converters have traditionally been limited to 6 or 8 bits resolution with the conversion rates of 10-40Ms/s.The disadvantages of flash ADC are the area and power requirements of the 2^N-1 comparators. So,To achive High resolutions with Lower power consumpution Two-step ADCs,pipelined ADCs are introduced to the Flash ADC archietecture.        

## Normal flash ADC   
It is formed of a series of comparators, each one comparing the input signal to a unique reference voltage. The comparator outputs connect to the inputs of a priority encoder circuit, which then produces a binary output. The following illustration shows a 3-bit flash ADC circuit:

![three-bit-flash-ADC-circuit_2](https://user-images.githubusercontent.com/110079790/217727478-d96bb606-066b-4256-9885-c87ad3e39f6f.jpg)

Vref is a stable reference voltage provided by a precision voltage regulator as part of the converter circuit, not shown in the schematic. As the analog input voltage exceeds the reference voltage at each comparator, the comparator outputs will sequentially saturate to a high state. The priority encoder generates a binary number based on the highest-order active input, ignoring all other active inputs.

When operated, the flash ADC produces an output that looks something like this:

![analog-input-digital-output](https://user-images.githubusercontent.com/110079790/217728843-af300135-3b83-4b29-9fac-341f427c6425.jpg)
