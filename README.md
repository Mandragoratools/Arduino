#Temporizador 
Copyrigth (c) Mandragora Tools 2016

Especial agradecimiento

[mandragoratools@gmail.com](mailto:mandragoratools@gmail.com)

[http://bit.ly/mandragoratools](http://bit.ly/mandragoratools)

*Especial agradecimiento a Alfaville, Lucario448  y surbyte


#¿Que es Temporizador?

Temporizador es una libreria escrita para Arduino en general, que nos sirve para programar transcursos de tiempo y ejecutar acciones transcurrido el tiempo indicado.

Nos sirve para sustituir la función delay(); en nuestros sckechts y evitar así retardos indeseados.

#Referencia

Temporizador temp;   --------> Instanciar el temporizador, usaremos "Temporizador" seguido del nombre que deseemos en este caso "temp".

temp.temporizar(0,0,2,0,0); --------> En esta linea programaremos el tiempo deseado. en este caso 2 minutos.



#Tener en cuenta

-La 1ª cifra de la función es la correspondiente a los dias.

-La 2ª cifra de la función es la correspondiente a las horas.

-La 3ª cifra de la función es la correspondiente a los minutos.

-La 4ª cifra de la función es la correspondiente a los segundos.

-La 5ª cifra de la función es la correspondiente a los milisegundos.

*Ejemplo: temp.temporizar1(1  ,  3   ,   40    ,   20   ,   100);

En este caso 1 dia 3 horas 40 minutos  20 segundos y 100 milisegundos.




#Usos
  
#include <Temporizador.h>

Temporizador temp; //-----> Declaramos una instancia  del temporizador

void setup() {
pinMode(2,OUTPUT); //-----> Declaramos el pin 2 como salida
temp.iniciar(0,0,0,1,0);//-----> Iniciamos el temporizador por primera ves en este caso a un segundo
}

void loop() {
//comprobamos si el tiempo definido ha transcurrido
if(temp.completado()){ 
  digitalWrite(2,!digitalRead(2)); //-----> En este caso al transcurrir el tiempo indicado invertimos el estado del pin 2
  timer1.iniciar(0,0,0,1,0); //-----> volvemos a iniciar el temporizador para que se repita de nuevo en modo bucle
}
}


*Podemos declarar tantas instancias como nos haga falta.


