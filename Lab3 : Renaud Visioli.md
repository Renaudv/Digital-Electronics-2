# Lab 3: RENAUD_VISIOLI

Link to your `Digital-electronics-2` GitHub repository:

   [https://github.com/Renaudv/Digital-Electronics-2](https://github.com/Renaudv/Digital-Electronics-2)


### Data types in C

1. Complete table.

| **Data type** | **Number of bits** | **Range** | **Description** |
| :-: | :-: | :-: | :-- | 
| `uint8_t`  | 8 | 0, 1, ..., 255 | Unsigned 8-bit integer |
| `int8_t`   | 8 | -128, -126, ..., 126, 127 | 8-bit integer |
| `uint16_t` | 16 | 0 to 65535 | Unsigned 16-bit integer |
| `int16_t`  | 16 | -32768 to 32767 | 16-bit integer |
| `float`    | 32 | -3.4e+38, ..., 3.4e+38 | Single-precision floating-point |
| `void`     | 0 | /!\ No Data | Void |


### GPIO library

1. In your words, describe the difference between the declaration and the definition of the function in C.
   * Function declaration : Before using a function for the first time we have to declared it. The declaration of the function is here to indicate what the function is (name, argument, returned data etc)

   * Function definition : The function definition is the body of the function, what the function does. It's the line and the

2. Part of the C code listing with syntax highlighting, which toggles LEDs only if push button is pressed. Otherwise, the value of the LEDs does not change. Use function from your GPIO library. Let the push button is connected to port D:

```c
    // Configure Push button at port D and enable internal pull-up resistor
    // WRITE YOUR CODE HERE
    // Infinite loop
    while (1)
    {
        // Pause several milliseconds
        _delay_ms(BLINK_DELAY);
        // WRITE YOUR CODE HERE
    }
```


### Traffic light

1. Scheme of traffic light application with one red/yellow/green light for cars and one red/green light for pedestrians. Connect AVR device, LEDs, resistors, one push button (for pedestrians), and supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values!

  ![image](https://user-images.githubusercontent.com/91612064/146560110-0eed351f-2e1a-4e44-8086-abf1c8ee7a7d.png)
