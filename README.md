# Learning IoT on PIC10f200

Need to have:

1. PIC10f200 chip
2. PCkit3 or any other device to flash the chip

Software:

1. MPLAB X IDE

Chip pinout:

1. Vdd - POWER
2. Vss - GROUND
3. GP2/T0CKI/FOSC4 - GPIO for i&o OR other stuff
4. GP1/ICSPCLK - GPIO for i&o OR in circuit serial programming clock for flashing program
5. GP0/ICSPDAT - GPIO for i&o OR in circuit serial programming data for flashing program
6. GP3/~MCLR/Vpp - GPIO for i only OR not CLEAR button OR other stuff

## Resources

Datasheet: https://ww1.microchip.com/downloads/en/DeviceDoc/40001239F.pdf
Youtube tutorial: https://www.youtube.com/watch?v=TvsLWEJ4kNI&list=PLfYdTiQCV_p4b7kQh-rnBs5UtgzQ6Ij-V&index=1

TO BE CONTINUED...

```
#include <xc.h>
#pragma config WDTE = OFF, CP = OFF, MCLRE = OFF

#define _XTAL_FREQ 4000000  // Define the clock frequency as 4 MHz

void main() {
    TRIS = 0b0000;  // Set all pins as outputs
    while (1) {
        GPIObits.GP0 = 1; // Turn on LED on GP0 (Pin 2)
        __delay_ms(500);
        GPIObits.GP0 = 0; // Turn on LED on GP0 (Pin 2)
        __delay_ms(500);
    }
}

```
