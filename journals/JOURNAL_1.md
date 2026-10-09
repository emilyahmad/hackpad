I was working on this macropad as my first hardware project for Stasis back in April I think, but the guide was really hard for me to follow, so I finished making the PCB and tried to submit the project without any CAD or firmware (not cooking).

A few months ago I saw a really cute video of these girls with keychains that had keycaps of toasted bread, but they kind of looked like slightly burnt marshmallows to me, which gave me the idea to make a really cute s'mores themed macropad for end of summer/beginning of fall. I feel like the s'mores components will actually fit well into the design, as you can see below:

[Little sketch](/images/prototype1.png)

I might just make the PCB from scratch for practice and I want to adjust it to a small 1x3 rather than current 2x3.

Shoot I'm actually reconsidering this looking at my old design. It wouldn't be that hard to add a rotary or an OLED and that would make it much more useful. Back to the drawing board?

[Another sketch](/images/prototype2.png)

I'll plan on a 2x2 with an OLED and USB-C for power, I guess it'll just have to be plugged in at all times when I use it?

Instead of the SEEEDUINO-XIAO I'll use the XIAO-ESP32S3 I have. I keep forgetting if I have the c3 or s3. I think c3.

I just realized I don't need a USB-receptable or anything, I'll just use the USB-C on the xiao, I just need to make sure I expose it and in general, place the C3 carefully.

+ What's the difference between 3v3 and VUSB pin?
Correspond to different power rails, we won't use VUSB (5V)

+ If you're not using pins on an MCU in a wiring diagram should you add a no connect flag?
Yes

[General placement](/images/smorespad_general_wiring.png)
I'm planning to wire it like this.

[Schematic](/images/smorespad_schematic.png)
This is what I've got, I'll double check with Claude. Claude mentioned:

+ Check if OLED contains I2C pull ups (Me & Claude çouldn't find it in the datasheet, Google says it's built in)
Because adding an additional 4.7 Ω resistor won't damage or make it slower, I'll add it between the SDA and SCL pins connecting to the OLED.

[Added resistors](/images/added_resistors.png)

+ Where should you add pwr_flags vs 3.3V in kicad?
Where power enters from an external source: I'll add to the VCC_3.3V pin on the C3.

+ Should I add a pwr_flag to the GND output of the C3 as well?

I'll probably do through-hole resistors because that's easier to solder. For assigning the footprint, I'll expand the Resistor_THT and choose based on size and power rating. For a 4.7K resistor, [this axial](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/CF14JT4K70/1741428?gclsrc=aw.ds&gad_source=4&gad_campaignid=20682878391&gbraid=0AAAAADrbLlhHagyj9VcMYXw5Jg6t3uN1_&gclid=CjwKCAjwoaLWBhAWEiwAnyitu0q7ZIoBEf24n7WvusGYdJZPNJ8Uxk2ilCPZ5ONNjpV8P_V0X50U-RoCQjoQAvD_BwE) is 0.25W and 0.091" Dia x 0.236" L (2.30mm x 6.00mm). If the hole diameter must be 0.1 mm to 0.3 mm larger than the resistor lead diameter, I need a footprint that's around 2.4 - 2.6 mm.

```
Resistor_THT:R_Axial_DIN0204_L3.6mm_D1.6mm_P7.62mm_Horizontal
```
L3.6mm: barrel/body length, D1.6mm: body diameter, P7.62mm: pitch/center-to-center distance - still don't really understand but this needs to match. Horizontal/vertical is the mounting orientation - I didn't know that actually mattered.

I'll look for the actual part I want to buy before assigning the footprint to make sure the pitch matches. I should just need 2 4.7K resistors. I'm kind of scared to use Aliexpress for now so I'll get a more expensive option that arrives earlier from Amazon that describes the body length and diameter as well as pitch. 

[This one](https://www.amazon.com/dp/B07HDFHPP3?niid=nl_cl_lst_a_1_1&ref_=nl_cl_lst_a_1_1&nrid=AMSVW953F9Z4BAB6X13X&th=1) approximates
Shell (body) length: 6mm
Max body diameter: 2.5mm

So I'll look for a footprint similar to L6mm_D2.5mm
[Resistor visual](/images/resistor_visual.png)
and place it vertically to better fit the board. Next time I might just surface mount & PCBA it. When it arrives I have to mesaure the body and make sure its body is within .5 mm and choose Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P2.54mm_Vertical

[Resistor visual](/images/footprints_assigned.png)


[datasheet](https://www.seielect.com/catalog/SEI-CF_CFM.pdf)

+ Switches have no external pull-up so use INPUT_PULLUP and read them as active-low

+ Swap 3.3v with PWR_FLAG pin or just ignore?