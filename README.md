### Hola 👋, Mi nombre es Jorge Celis 
#### Soy el creador de OnlyCircuits
Esta página está destinada para las personas interesadas en la electrónica y programación

Habilidades: C/C++, VHDL, CUPL, Python

#define F_CPU 16000000		// Frecuencia del cristal (Sistema de Reloj)
#define BAUD_RATE 9600		// Velocidad de transferencia por canal serial

#include <avr/io.h>
#include <util/delay.h>		// Para usar funciones de retardo ('_delay_ms')

void usart_init (void) {
	UCSR0B = (1<<TXEN0) ;								// Habilitación del Transmisor
	UCSR0C = (1<< UCSZ01)|(1<<UCSZ00);	// 8 bits, 1 bit de paro, sin Paridad
	UBRR0L = 103;											  // Velocidad, en Bauds, de la comunicación
}
void usart_send (unsigned char ch) {
	while (! (UCSR0A & (1<<UDRE0)));	// Espera hasta que UDR0 esté vacío
	UDR0 = ch ;
}
void NuevaLinea(void) {
	usart_send(0x0D);			// Retorno de Carro (Carriage Return)
	usart_send(0x0A);			// Nueva Línea (Line Feed)
}

int main(void)
{
	char nombre[5] = "Hola";
    usart_init();
	
    while (1) 
    {
		for (int c = 0; c < 5; c++)
		{
			usart_send(nombre[c]);
		}
		
		NuevaLinea();
		_delay_ms(1000);
    }
}

- 🔭 Estoy trabajando en proyectos electrónicos con microcontroladores y FPGAs 
- 🌱 Estoy aprendiendo otros lenguajes de programación para el uso de microcontroladores, FPGAs así como usar sus softwares 
- 👯 Quiero colaborar con Alguna marca de componentes electrónicos, pero mi sueño sería que Microchip viera mi trabajo 
- 📫 Cómo contactarme: onlycircuits321@gmail.com 


[<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/github.svg' alt='github' height='40'>](https://github.com/https://github.com/OnlyCircuits)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/instagram.svg' alt='instagram' height='40'>](https://www.instagram.com/https://www.instagram.com/only_circuits//)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/twitter.svg' alt='twitter' height='40'>](https://twitter.com/https://twitter.com/OnlyCircuits)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/youtube.svg' alt='YouTube' height='40'>](https://www.youtube.com/channel/https://www.youtube.com/channel/UC2dgur8_ip1ran6Svu5eWwQ)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/icloud.svg' alt='website' height='40'>](https://beacons.ai/onlycircuits)  

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=https://github.com/OnlyCircuits)](https://github.com/anuraghazra/github-readme-stats)

