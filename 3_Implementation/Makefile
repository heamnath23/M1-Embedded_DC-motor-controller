#ifndef F_CPU
#define F_CPU 4000000UL
#endif

#include <avr/io.h>    
#include <util/delay.h>  

#define en12  (1<<PD2)
#define a1 (1<<PD4)
#define a2 (1<<PD5)
 
int main(void){
    DDRD |= en12 | a1 | a2;
    PORTD |= en12;

    while(1){
        //clockwise rotation
        PORTD &= ~a1;
        PORTD |= a2;

        //stop motor
        PORTD &= ~a1 | ~a2;    
        _delay_ms(3000);    //3 sec delay
        
        //anti-clockwise rotation
        PORTD |= a1;
        PORTD &= ~a2;
        
        PORTD &= ~a1 | ~a2;    //stop motor
        _delay_ms(3000);
    }
return(0);
} 
