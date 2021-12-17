# Lab 7: Renaud Visioli

Link to this file in your GitHub repository:

[https://github.com/Renaudv/Digital-Electronics-2/](https://github.com/Renaudv/Digital-Electronics-2/)

### Analog-to-Digital Conversion

1. Complete table with voltage divider, calculated, and measured ADC values for all five push buttons.

   | **Push button** | **PC0[A0] voltage** | **ADC value (calculated)** | **ADC value (measured)** |
   | :-: | :-: | :-: | :-: |
   | Right  | 0&nbsp;V | 0   | 0 |
   | Up     | 0.495&nbsp;V | 101 | 99 |
   | Down   |    1.203   |  246   | 257 |
   | Left   |   1.96    |   400  | 409 |
   | Select |    3.18   |   650  | 639 |
   | none   |    5   |  1023   | 1023 |

2. Code listing of ACD interrupt service routine for sending data to the LCD/UART and identification of the pressed button. Always use syntax highlighting and meaningful comments:

```c
/**********************************************************************
 * Function: ADC complete interrupt
 * Purpose:  Display value on LCD and send it to UART.
 **********************************************************************/
ISR(ADC_vect)
{
    uint16_t value = 0;
    char lcd_string[4] = "0000";

    value = ADC;                  // Copy ADC result to 16-bit variable
    itoa(value, lcd_string, 10);  // Convert decimal value to string

    // WRITE YOUR CODE HERE 
    lcd_gotoxy(8, 0);
    lcd_puts("   ");
    lcd_gotoxy(8,0);
    lcd_puts(lcd_string);
    
    uart_puts(lcd_string);
    uart_puts(" ")
    
     itoa(value, lcd_string, 16);
     lcd_gotoxy(13, 0);
    lcd_puts("   ");
    lcd_gotoxy(13,0);
    lcd_puts(lcd_string);
    
    if(value==1022){
      lcd_gotoxy(8, 1);
      lcd_puts("   ");
      lcd_gotoxy(8,1);
      lcd_puts("none");
    
    }
    
    if(value>=97 && value<=103){
      lcd_gotoxy(8, 1);
      lcd_puts("   ");
      lcd_gotoxy(8,1);
      lcd_puts("up);
    
    }
    if(value>=400 && value<=405){
		lcd_gotoxy(8, 1);
		lcd_puts("     ");
		lcd_gotoxy(8, 1);
		lcd_puts("left");
		
	}
	if(value>=240 && value<=250){
		lcd_gotoxy(8, 1);
		lcd_puts("     ");
		lcd_gotoxy(8, 1);
		lcd_puts("down");
		
	}
	if(value>=647 && value<=653){
		lcd_gotoxy(8, 1);
		lcd_puts("     ");
		lcd_gotoxy(8, 1);
		lcd_puts("select");
		
	}
	if(value==0){
		lcd_gotoxy(8, 1);
		lcd_puts("     ");
		lcd_gotoxy(8, 1);
		lcd_puts("right");
	}
}
```

### UART communication

1. (Hand-drawn) picture of UART signal when transmitting three character data `De2` in 4800 7O2 mode (7 data bits, odd parity, 2 stop bits, 4800&nbsp;Bd).

   ![your figure](https://media.discordapp.net/attachments/753864656040362004/921476833722109952/IMG_20211217_195929.jpg?width=497&height=662)

2. Flowchart figure for function `uint8_t get_parity(uint8_t data, uint8_t type)` which calculates a parity bit of input 8-bit `data` according to parameter `type`. The image can be drawn on a computer or by hand. Use clear descriptions of the individual steps of the algorithms.

   ![your figure](https://media.discordapp.net/attachments/753864656040362004/921442834576445440/IMG_20211217_174408.jpg?width=497&height=662)

### Temperature meter

Consider an application for temperature measurement and display. Use temperature sensor [TC1046](http://ww1.microchip.com/downloads/en/DeviceDoc/21496C.pdf), LCD, one LED and a push button. After pressing the button, the temperature is measured, its value is displayed on the LCD and data is sent to the UART. When the temperature is too high, the LED will start blinking.

1. Scheme of temperature meter. The image can be drawn on a computer or by hand. Always name all components and their values.

   ![your figure](https://media.discordapp.net/attachments/753864656040362004/921476833432707092/IMG_20211217_195926.jpg?width=497&height=662)
