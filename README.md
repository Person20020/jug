<img width="100%" alt="Jug Logo wide no fill" src="https://github.com/user-attachments/assets/d46b12e5-16b6-4395-81ab-9a57c222ad11" />

# Jug

A 6x3 column staggered split keyboard with a large thumb cluster.

![picture](https://hc-cdn.hel1.your-objectstorage.com/s/v3/e3614a3b6a1b1744612c7d60f0511643e53c0c7f_pxl_20250727_031849672_3.jpg)

![jug render](https://hc-cdn.hel1.your-objectstorage.com/s/v3/eb3f01ef514535af3f6a53b21dcda8743f94412f_jug_case_2025-jul-04_06-37-14am-000_customizedview29367406515.png)

The jug is a 6x3 column staggered split keyboard with 46 keys. It has a 5 key thumb cluster extending out to reduce reaching back with your thumb. It uses USB C for interconnect and includes two indicator leds per side for caps/num lock and layer (eg. Colemak vs QWERTY).

The PCB supports both hotswap sockets and directly soldering the switches. It is fully reversible and uses soldered jumpers for the MCU, a RP2040 Zero. 

All components are placed so that the case sides are exact mirrors.

![pcb](https://hc-cdn.hel1.your-objectstorage.com/s/v3/060a25b877864548f696b6b857fbd78fa6695b34_jug-pcb-for-render_v1_2025-jul-07_02-14-08am-000_customizedview13108977982.png)
![schematic](https://hc-cdn.hel1.your-objectstorage.com/s/v3/7e51c1129ae840b9626f04786beea81ee03fceef_image.png)
![routing](https://hc-cdn.hel1.your-objectstorage.com/s/v3/e317385385acf5c65a0750020bb4ffa397627bee_image.png)

## Parts

### Electronics

| Part                                     | Count | Price ($)                    | Link                                                                                                                                                                                                                                                                                    |
| ---------------------------------------- | ----- | ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RP2040 Zero                              | 2     | ~4 each                      |                                                                                                                                                                                                                                                                                         |
| MX Switches                              | 46    | ~20-30                       |                                                                                                                                                                                                                                                                                         |
| Hotswap Sockets (optional)               | 46    | ~10 for 70 on AliExpress     |                                                                                                                                                                                                                                                                                         |
| 1n4148 Diodes                            | 46    | ~2 for 100 on AliExpress     |                                                                                                                                                                                                                                                                                         |
| USB C Ports                              | 2     | 0.40 (5 min order on lcsc)   | [https://lcsc.com/product-detail/image/GT-USB-7010ASV_C2988369.html](https://lcsc.com/product-detail/image/GT-USB-7010ASV_C2988369.html)                                                                                                                                                |
| 1206 SMD LEDs (I used red and blue leds) | 4     | 0.42 (100 min order on lcsc) | [blue](https://lcsc.com/product-detail/image/XL-3216UBC_C965827.html) or [red](https://lcsc.com/product-detail/image/XL-1608SURC-06_C965799.html) |
| 1206 35.7 ohm SMD Resistors              | 4     | 0.18                         | [https://lcsc.com/product-detail/image/RC1206FR-0735R7L_C488810.html](https://lcsc.com/product-detail/image/RC1206FR-0735R7L_C488810.html)                                                                                                                                              |
| 1206 5.1k ohm SMD Resistors              | 2     | 0.22                         | [https://lcsc.com/product-detail/image/FRC1206J512-TS_C2907509.html](https://lcsc.com/product-detail/image/FRC1206J512-TS_C2907509.html)                                                                                                                                                |


### Other

| Part                                | Count |
| ----------------------------------- | ----- |
| 1u Keycaps                          | 42    |
| 1.5u Keycaps                        | 4     |
| 8mm m2 Standoffs                    | 14    |
| m2 x 4mm Screws                     | 28    |
| m2 x 12mm Screws                    | 4     |
| m3 x 12mm Screws                    | 12    |
| m3 Heat Set Inserts (5mm OD, 4mm L) | 12    |

I used socket head screws with hex drives. For the m2 screws screwed into the standoffs on the top (from the plate side, there are 14 of these) you will need to have screws that have a low enough head so that they don't hit the keycaps. I used [these](https://www.aliexpress.us/item/3256804883804669.html). 

If you don't want to buy keycaps you can also print some like the [ScottoCaps](https://github.com/joe-scotto/scottokeebs/tree/main/Extras/ScottoCaps).


## Case

The case can be printed in its provided orientation, with the bottom to the build plate. The screw holes have sacrificial bridges in them to allow it to print cleanly. After printing, use a knife to cut through them. Other than that there should be no cleanup necessary.


## Firmware

I made both plain QMK and a Vial version of the firmware. They both have Colemak for the base layer with QWERTY as a second layer. You can set QWERTY as the base layer by moving the ` = 0` to `_QWERTY` from `_COLEMAK` in the keymap.c file, changing this:

```
enum layer_number {
    _COLEMAK = 0,
    _QWERTY,
    _LOWER,
    _RAISE,
    _ADJUST
};
```
to this:
```
enum layer_number {
    _COLEMAK,
    _QWERTY = 0,
    _LOWER,
    _RAISE,
    _ADJUST
};
```
