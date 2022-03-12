
#include "own_drivers_and_func.h"

const int for_delay = 100000; 
void my_delay_ms(uint32_t time) 
{								
	for (uint32_t i = 0; i < (time * for_delay); i++)
	{
	}
}

void button_init(void)
{
	uint32_t *pRccAhb1enr = (uint32_t *)0x40023830;
	*pRccAhb1enr |= (1 << 0);						
	/*This is optional because its input by default*/
	/*------*/
	uint32_t *pGpiodModeReg = (uint32_t *)0x40020000; 
	*pGpiodModeReg &= ~(1 << 0);					 
	*pGpiodModeReg &= ~(1 << 1);
	/*------*/

	uint32_t *pGpioPuPdReg = (uint32_t *)0x4002000C; 
	*pGpioPuPdReg |= (1 << 1);						
}

void led_init_all(void)
{													  //(for Gpio D)
													  // for clocking and making it input or output(here)
	uint32_t *pRccAhb1enr = (uint32_t *)0x40023830;	  

	*pRccAhb1enr |= (1 << 3); // enable GPIOD (GPIODEN) pg.no 265
	// configure it as General purpose output mode
	//  see pg.no 281 -> GPIO port mode register, MODERy[1:0] for understanding
	*pGpiodModeReg |= (1 << (2 * LED_GREEN));  // setting MODER12 as an output port
	*pGpiodModeReg |= (1 << (2 * LED_ORANGE)); // setting MODER13 as an output port
	*pGpiodModeReg |= (1 << (2 * LED_RED));	   // settingMODER14 as an output port
	*pGpiodModeReg |= (1 << (2 * LED_BLUE));   // setting MODER15 as an output port

	led_off(LED_GREEN);
	led_off(LED_ORANGE);
	led_off(LED_RED);
	led_off(LED_BLUE);
}

void led_on(uint8_t led_no)							  // here this will on led for given LED pin
{													  // for outputting data
	uint32_t *pGpiodDataReg = (uint32_t *)0x40020C14; //(GPIOx_ODR) + 0x14(offset)
	*pGpiodDataReg |= (1 << led_no);
}

void led_off(uint8_t led_no)						 
{													  
	uint32_t *pGpiodDataReg = (uint32_t *)0x40020C14; 
	*pGpiodDataReg &= ~(1 << led_no);
}

int btn_press(void) // Done by Nyalam Praveenraj
{ // for inputting button press data and returns button count
	int count = 0;
	int hfmilsec = 10000000;			
	uint32_t *pGpioaDataReg = (uint32_t *)0x40020010; 
	while (hfmilsec--)
	{
		if ((*pGpioaDataReg) & (1 << user_btn)) // Checking if the switch is pressed or not (Polling)
		{										// check if the button is pressed or not
			my_delay_ms(150);
			count++;
			if (count > 4)
				count = 0;
		}
	}
	return count;
}
