 linea 44 
  let randomNumber = Math.random() * 10;
esta colocando numeros aleatorios (hasta decimales) entre 0 y 10, segun requerimiento es numeros ENTEROS, entre 1 y 100
correccion: 
  let randomNumber = Math.floor(Math.random() * 100) + 1;

---------------------------------------------------------------------------------------------------------  linea 46
  const ATTEMPS = 5;
  solo permite 5 intentos, y segun requerimientos son 10
  const ATTEMPS = 10;

---------------------------------------------------------------------------------------------------------
linea 49 
problemas al seleccionar un elemento que no existe si no tiene un punto antes.

const lowOrHi = document.querySelector('lowOrHi'); antes

const lowOrHi = document.querySelector('.lowOrHi'); despues 

---------------------------------------------------------------------------------------------------------
linea 57
antes de comparar hay que conventir a numero 
 antes:           let userGuess = guessField.value;
 correccion :     let userGuess = Number(guessField.value);

---------------------------------------------------------------------------------------------------------

se agrego validacion para verificar que se ingrese solo numeros enteros y nungun otro tipo de caracter.
   
     if (userGuess < 1 || userGuess > 100 || isNaN(userGuess)) {
    lastResult.textContent = 'Número no válido. Debe estar entre 1 y 100.';
    lastResult.style.color = 'Blue'; 
    guessField.value = '';
    guessField.focus();
    return; 
  }

  ademas se agrego una instruccion para eliminar dicha linea luego de agragar un caracter valido 
      lastResult.textContent = ''; 
---------------------------------------------------------------------------------------------------------

linea 77 y 78 
if(userGuess === randomNumber) {
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'black';

problemas: si el numero es igual a numero random, el usuario ganó, y segun requerimientos el mensaje debe ser en verde

solucion :

 lastResult.textContent = 'Felicitaciones! adivinaste el número!' + randomNumber;
 lastResult.style.backgroundColor = 'green';

---------------------------------------------------------------------------------------------------------
linea 82 : 
else if(guessCount === ATTEMPS) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';

problema: aqui nos esta diciendo que al llegar al numero de intentos, nos diga que ganamos, pero en realidad perdimos.

solucion: se corrije mensaje

} else if(guessCount === ATTEMPS) {
lastResult.textContent = '!!!Pérdistes!!!' ;
---------------------------------------------------------------------------------------------------------

linea 88

        lowOrHi.textContent = 'El número es mayor!';
solucion:
        lowOrHi.textContent = 'Incorrecto! El número es mayor!';

Linea 90
mensaje no cumple con lo requerido:
        lowOrHi.textContent = 'El número es menor!';
solucion:
        lowOrHi.textContent = 'Incorrecto! El número es menor!';


---------------------------------------------------------------------------------------------------------
linea 98
guessSubmit.addeventListener('click', checkGuess);

metodo mal escrito(letra "E" en minuscula ), por lo cual a hacer click en boton "ingresar numero aleatorio" no hace nada. 

solucion: guessSubmit.addEventListener('click', checkGuess);


mismo problema con la linea 106
antes:
resetButton.addeventListener('click', resetGame);
Despues:
resetButton.addEventListener('click', resetGame); 

---------------------------------------------------------------------------------------------------------
 linea 125
problema: no se determina en que rango se debe generar el numero
	  randomNumber = Math.floor(Math.random()) + 1;

solucion

	  randomNumber = Math.floor(Math.random() 100) + 1;
      se agrega el numero 100 para generar numereos de 0 a 100

---------------------------------------------------------------------------------------------------------

se elimina :

lastResult.textContent = 'incorrecto ';
lastResult.style.backgroundColor = 'green';


debido a que cada vez que se ingresaba un numero, no importando si era entero o no, este mensaje aparecia