Maybe next time should've used a keyboard matrix?
![keyboard matrix](https://i.ytimg.com/vi/7LyziNdFlew/sddefault.jpg)

Placing the switches/keys is so frustrating. I saw a youtube comment saying to use a plugin so I might just use that. I'm trying to do the grid spacing, setting a grid origin point and moving with reference but it's not working (this happened last time too, a few months ago and I wasn't able to figure it out)

New plan because the OLED is lowkey huge: put the C3 behind the OLED so the USB-C still sticks out, but the new design will look more like this:

![New placement](/images/general_placement2.png)

I'm planning to add ~ 1.5mm spacing between each component. Never mind, that looks huge in the 3D viewer. Oh but that's the indivudal switches, there's going to need to be space for the keycaps. I'll just keep them bordering each other, so no overlap.

Oh my gosh I didn't realize vertical mounting was like z-axis vertical.

![Vertical resistor mounting](/images/vertical_mount.png)

That's horrible when would I need that.

I'm going to change the OLED I use as well to something smaller. [These look cute](https://www.amazon.com/AITRIP-Display-Compact-Self-Luminous-Projects/dp/B0F5WPZJ92/ref=sr_1_3?crid=1W4R4XG6EKCV5&dib=eyJ2IjoiMSJ9.3XLdBWCYkPI47uifaPVXK99n5IV_giyShHyUTwhnWVEDP-yJQa0B5RzTQDlgrxDCSBCv30FgSrZCUTYryvVypnn40UWekQQI2bAbhrSGSkYcp7x-KUrSyH3ivYsNBqbA5B57mn4_AdDgzZp3m5RYfosxBzJAf01tTG9NzWauOoSeACfzrY_SQSsK9G-0B-RS-Z5E1zmI8CP4NRw2GmF2fZKC277QnFr_n7N2xnK2WdH990BNvNBRzgvqPAHG3AvXepj0D5ViaBcreogHT7AdI-a7xTj7ATU093yoKpsHg-g.wDJkpx_Bcac2kKQFXO91Q54QMV_RH7YsK3zA3Og26pk&dib_tag=se&keywords=OLED%2Bdisplay%2Bfor%2Bpcb%2Bpresoldered&qid=1791608771&s=industrial&sprefix=oled%2Bdisplay%2Bfor%2Bpcb%2Bpresoldered%2Cindustrial%2C92&sr=1-3&th=1) and are white, not finding any presoldered ones.

+ Should I just put correctly wired header pins on the PCB instead of an OLED footprint?
I guess so, this OLED works with header pins with 2.54 mm spacing.

Here's the updated schematic, I just need to change the resistor footprints to horizontal mounting and assign the right header pins.

![Header pins](/images/updated_OLED.png)

Debating if I get surface mounted resistors and have them with the board.. Nah. These are the new footprints:

![New footprints](/images/new_footprints.png)

Back to the PCB.