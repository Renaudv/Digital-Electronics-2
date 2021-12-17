# Lab 6: Renaud Visioli

Link to this file in your GitHub repository:

[https://github.com/Renaudv/Digital-Electronics-2](https://github.com/Renaudv/Digital-Electronics-2)


### LCD display module

1. In your words, describe what ASCII table is.
   * ASCII table: the american standard code for information interchange is a table that give a reference of 7 bit to use character in hexadecimal, binary and more

2. (Hand-drawn) picture of time signals between ATmega328P and LCD keypad shield (HD44780 driver) when transmitting three character data `De2`.

   ![your figure](https://cdn.discordapp.com/attachments/753864656040362004/921420441762017350/IMG_20211217_161544.jpg)


### Stopwatch

1. Flowchart figure for `TIMER2_OVF_vect` interrupt service routine which overflows every 16&nbsp;ms but it updates the stopwatch LCD approximately every 100&nbsp;ms (6 x 16&nbsp;ms = 100&nbsp;ms). Display tenths of a second and seconds `00:seconds.tenths`. Let the stopwatch counts from `00:00.0` to `00:59.9` and then starts again. The image can be drawn on a computer or by hand. Use clear descriptions of the individual steps of the algorithms.

   ![your figure](https://cdn.discordapp.com/attachments/753864656040362004/921418320555683840/IMG_20211217_160715.jpg)


### Custom characters

1. Code listing of two custom character definition. Always use syntax highlighting and meaningful comments:

```c
/* Variables ---------------------------------------------------------*/
// Custom character definition
uint8_t customChar[16] = {
    // WRITE YOUR CODE HERE
    0b01010,
    0b00100,
    0b10101,
    0b00100,
    0b00011,
    0b00001,
    0b01000,
    0b10111,
    
    0b01001,
    0b01110,
    0b10001,
    0b00011,
    0b11000,
    0b01010,
    0b11011,
    0b00100,
    
};
```


### Kitchen alarm

Consider a kitchen alarm with an LCD, one LED and three push buttons: start, +1 minute, -1 minute. Use the +1/-1 minute buttons to increment/decrement the timer value. After pressing the Start button, the countdown starts. The countdown value is shown on the display in the form of mm.ss (minutes.seconds). At the end of the countdown, the LED will start blinking.

1. Scheme of kitchen alarm; do not forget the supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values.

   ![your figure](https://media.discordapp.net/attachments/753864656040362004/921423565306351676/IMG_20211217_162811.jpg?width=497&height=662)
