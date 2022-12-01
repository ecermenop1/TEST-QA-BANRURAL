1. El botón que tiene como descripción "ingresar el número" no está ejecutando ninguna función
debido a que  el llamado del evento a la función es incorrecto


Error encontrado: evento addeventListener  mal escrito, por lo tanto no se ejecuta la función checkGuess
guessSubmit.addeventListener('click', checkGuess);
SOLUCIÓN:
guessSubmit.addEventListener('click', checkGuess);


2. Error encontrado: Los numeros aleatorios se están generando de 1 a 10 y se generan en decimales
let randomNumber = Math.random() * 10;
SOLUCIÓN: se cambia el 100 por el 10
let randomNumber = Math.floor(Math.random() * 100) + 1;

3. Error encontrado: El numero de intentos máximos es de 5 y en los requerimientos se solicitan 10 intentos como máximo.
const ATTEMPS = 5;
SOLUCIÓN: Se cambia el valor de la constante ATTEMPS a un valor de 10
const ATTEMPS = 10;


4. Error encontrado: No existe la validación para verificar si el valor ingresado es entero o decimal
y no existe ninguna alerta que notifique que el valor ingresado debe ser un numero entero.
SOLUCIÓN: Se agrego la siguiente condición que valida si el numero ingresado es entero o decimal

if(userGuess %1==0){
    }else{
    alert('debe ingresar un numero entero');
  }


6. Error encontrado: No se está llamando correctamente el id de tipo class
const lowOrHi = document.querySelector('lowOrHi');
SOLUCIÓN: Se le debe de colocar el . para que haga referencia al tipo class
const lowOrHi = document.querySelector('.lowOrHi');



7. Error encontrado: Las condiciones especificadas en el if y en los else if son incorrectas,
los colores backgroundcolor no son los los que se especifican en el requerimiento,
Los resultados que devuelve son incorrectos.

if(userGuess === randomNumber) {
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'black';
      lowOrHi.textContent = '';
      setGameOver();
    } else if(guessCount === ATTEMPS) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();
    } else {
      lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor = 'green';
      if(userGuess < randomNumber) {
        lowOrHi.textContent = 'El número es mayor!';
      } else if(userGuess > randomNumber) {
        lowOrHi.textContent = 'El número es menor!';
      }
    }


SOLUCIÓN: Se reestructuraron todos los condicionales y los datos correctos que debe de devolver

if(userGuess != randomNumber) {

      lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor = 'black';
      if(userGuess > randomNumber) {
        lowOrHi.textContent = 'El número es mayor!';
      } else if(userGuess < randomNumber) {
        lowOrHi.textContent = 'El número es menor!';
      }
     
    } else if(userGuess == randomNumber) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'green';
      lowOrHi.textContent = '';
      setGameOver()
    } 
    
    if(guessCount==ATTEMPS) {
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'red';
      lowOrHi.textContent = '';
      setGameOver()
    }












