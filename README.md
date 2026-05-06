# Macropad ᶻ 𝗓 𐰁 .ᐟ

A simple macropad with an OLED screen, 1 LED and 6 switches. Have a few different ideas on how I'll use it/firmware, some ideas: keyboard shortcuts for git commands, game controller, MIDI controller. Made using @Alex Ren's hackpad guide and Joe Scotto's keyboard guides.

# Photos

| Schematic                                  | PCB                            | 3D Viewer                    |
| ------------------------------------------ | ------------------------------ | ---------------------------- |
| ![Schematic](/images/schematic.png) | ![PCB](/images/pcb.png) | ![3D](/images/3d.png) |

# BOM (Components)

| Item                   | Purpose           | Quantity   | Cost   | Source                                                                |
| ---------------------- | ----------------- | ---------- | ------ | --------------------------------------------------------------------- | ------------ |
| D1                     | RGB LED           | 1 (MOQ 5)  | $0.43  | [LCSC C5149201](https://www.lcsc.com/product-detail/C5149201.html)    |
| D2, D3, D4, D5, D6, D7 | Signal Diode      | 6 (MOQ 50) | $1.09  | [LCSC C258182](https://www.lcsc.com/product-detail/C258182.html)      |
| J1                     | OLED 128x32       | 1          | $2.24  | [LCSC C5248081](https://www.lcsc.com/product-detail/C5248081.html)    |
| U1                     | Seeed XIAO RP2040 | 1          | $10.99 | [Amazon](https://www.amazon.com/gp/product/B0DRNSV5CS) (pre-soldered) | pre-soldered |

# Assembly BOM

| Item                            | Purpose                             | Quantity   | Cost             | Source                                                                                                |
| ------------------------------- | ----------------------------------- | ---------- | ---------------- | ----------------------------------------------------------------------------------------------------- |
| PCB                             | functionality through MCU, mounting | 5          | $2, total $21.60 | JLCPCB                                                                                                |
| XDA keycaps (black transparent) | cover switches                      | 20         | $11.99           | [Amazon](https://www.amazon.com/gp/product/B0CQ2YM5FM/ref=ox_sc_act_image_1?smid=A1T1IN9BGLZH2U&th=1) |
| Solder Tip Cleaner              | clean flux                          | 1          | $9.99            | [Amazon](https://www.amazon.com/gp/product/B0CNVS7BFZ/ref=ox_sc_act_image_3?smid=A328EBN1BG6NU5&th=1) |
| Solder Wire                     | to solder                           | 1          | $9.99            | [Amazon](https://www.amazon.com/gp/product/B0B6397413/ref=ox_sc_act_image_4?smid=A2T4V9F5BIUYS6&th=1) |
| Mini Soldering Iron             | to solder                           | 1          | $39.99           | [Amazon](https://www.amazon.com/gp/product/B096X6SG13/ref=ox_sc_act_image_5?smid=AS24VHUSR1W5D&psc=1) |
| S1, S2, S3, S4, S5, S6          | MX switches, brown                  | 6 (MOQ 20) | $8.99            | [Amazon](https://www.amazon.com/gp/product/B0888JHM58/ref=ox_sc_act_image_6?smid=A2U3R73MNHPWPS&th=1) |

Macropad Total: $57.33
with Soldering kit: $117.30
