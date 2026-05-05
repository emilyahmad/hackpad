# Monkeyboard

A simple macropad with an OLED screen, 1 LED and 6 switches. Have a few different ideas on how I'll use it/firmware, some ideas: keyboard shortcuts for git commands, game controller, MIDI controller. Made using @Alex Ren's hackpad guide and Joe Scotto's keyboard guides.

# Photos

| Schematic                                  | PCB                            | 3D Viewer                    |
| ------------------------------------------ | ------------------------------ | ---------------------------- |
| ![Schematic](hackpad/images/schematic.png) | ![PCB](hackpad/images/pcb.png) | ![3D](hackpad/images/3d.png) |

# BOM

| Item                   | Purpose                                | Quantity | Cost | Source  |
| ---------------------- | -------------------------------------- | -------- | ---- | ------- |
| D1                     | LED_SK6812MINI                         | 1        | $0   | idk yet |
| D2, D3, D4, D5, D6, D7 | Diode_DO-35                            | 6        | $0   | idk yet |
| J1                     | OLED_128x32                            | 1        | $0   | idk yet |
| U1                     | XIAO-Generic-Hybrid-14P-2.54-21X17.8MM | 1        | $0   | idk yet |

Total: ?

<!--
```
 _
//\
V  \
 \  \_
  \,'.`-.
   |\ `. `.
   ( \  `. `-.                        _,.-:\
    \ \   `.  `-._             __..--' ,-';/
     \ `.   `-.   `-..___..---'   _.--' ,'/
      `. `.    `-._        __..--'    ,' /
        `. `-_     ``--..''       _.-' ,'
          `-_ `-.___        __,--'   ,'
             `-.__  `----"""    __.-'
                  `--..____..--'

```

reference
|RP2040|$0.94|https://www.lcsc.com/product-detail/C2040.html?s_z=s_p_RP2040&spm=wm.ssy.bg.0.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUVBfR1haUjsOAxUeFF5JWBYZEEoKFBINSQcJGk4%3D|
|Crystal oscillator|$0.07|https://www.lcsc.com/product-detail/C9002.html?s_z=s_q_CRYSTAL%252012MHZ&spm=wm.ssy.bg.0.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUVFTRlVXXzsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slRVFaV0oOAwwC|
|MCP1700 LDO, 3.3V|$0.98|https://www.lcsc.com/product-detail/C39051.html?s_z=n_q_mcp1700%2520tt&spm=wm.ssy.bg.16.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUVJRR1hcXjsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D|
|USB-C port, 16-pin|$0.08|https://www.lcsc.com/product-detail/C2988369.html?s_z=n_q_usb%2520c%252016&spm=wm.ssy.bg.0.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUVNSRVVYVzsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slRFheUlVIHxUDCw%3D%3D|
|W25Q128JVSIQ flash memory|$1.96|https://www.lcsc.com/product-detail/C97521.html?s_z=s_q_W25Q128JVSIQ&spm=wm.ssy.bg.0.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUVxWRFlWVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slRVhWX1dQTk8GEwkK|
|PCM5102A DAC|$1.02|https://www.lcsc.com/product-detail/C107671.html?s_z=n_q_pcm5102a&spm=wm.ssy.bg.1.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUV1XRVlaVjsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D|
|PAM8302AAD speaker amplifier|$0.21|https://www.lcsc.com/product-detail/C112137.html?s_z=n_q_pam8302aad&spm=wm.ssy.bg.0.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUV1SQFJbUzsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slRlFZUVNXWQkaCgg%3D|
|BQ25185 battery charging IC|$1.66|https://www.lcsc.com/product-detail/C19725033.html?s_z=s_p_BQ25185DLHR&spm=wm.ssy.bg.0.xh&lcsc_vid=E1ENUAdXFlVdBAVSQFBZUQJQRFEMVgIFEgVcAgBRQgQxVlNRQFNbUV1fQ1RWVzsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slRlBcVldRWQkaCgg%3D|
|SMD tactile switch, 6x6mm|$0.03|https://www.lcsc.com/product-detail/C49234152.html?s_z=n_q_5x5mm%2520button&spm=wm.ssy.bg.0.xh&lcsc_vid=RlQIVAdXEVQKUwJREwNdVlQAEQNaUAUCTlNbAgdURlMxVlNRQFJcUFFUTlhdUDsOAxUeFF5JWBYZEEoKFBINSQcJGk4%3D|
|Pin headers|$0.38|https://www.lcsc.com/product-detail/C2938459.html?s_z=h_q_pin%2520headers%252001x20&spm=wm.ssy.bg.1.xh&lcsc_vid=RlQIVAdXEVQKUwJREwNdVlQAEQNaUAUCTlNbAgdURlMxVlNRQFJcX1dVQFdZVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slRVhdX1BUQ08GEwkK|
|PCB|$0.42|https://cart.jlcpcb.com/quote?stencilLayer=2&stencilWidth=21&stencilLength=54&stencilCounts=5&plateType=1|
|Stencil|$3.05|https://cart.jlcpcb.com/quote?stencilLayer=2&stencilWidth=21&stencilLength=54&stencilCounts=5&plateType=1|

Total: $10.81 ($7.76 w/o stencil)

# Notes

meow
-
