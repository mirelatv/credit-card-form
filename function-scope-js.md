** FUNCIONES  GLOBALES

$(document).ready(function() {}

** VARIABLES LOCALES

 var $inputCard = $('#card-number');
  var $inputMonth = $('.input-month');
  var $inputYear = $('.input-year');
  var $buttonNext = $('#next');
  var regexOnlyNumbers = /^[0-9]+$/;
  var labelErrorOrSuccessMessages = $('label[for="card-number"]');


** FUNCION DE CALLBACK

$inputCard.on('input', function() {
    isValidCreditCard($(this).val().trim());
  });


**  FUNCION DE STATEMENT y FORMAN  PARTE  DE LA  PILA  DE EJECUCION.

function activeButton() {
    $buttonNext.attr('disabled', false);
  } 


function desactiveButton() {  
    $buttonNext.attr('disabled', true);
  } 

function longitud(input) {
    if (input.trim().length === 16) {
      return input;
    }
  }

 function soloNumeros(input) {
    var regex = /^[0-9]+$/;
    if (regex.test(input)) {
      return input;
    }
  }

function isValidCreditCard(numberCard) {
    var creditCardNumber = soloNumeros(longitud(numberCard));
    if (creditCardNumber !== undefined) {
      var arr = [];
      var sumaTotal = 0;
      for (var index = creditCardNumber.length - 1; index >= 0; index--) {
        arr.push(creditCardNumber[index]);
      }
      for (var index = 1; index < arr.length; index = index + 2) {
        arr[index] = arr[index] * 2;
        if (arr[index] >= 10) {
          arr[index] = arr[index] - 9;
        }    
       }


       
** SCOPE  ALCANCE LOCAL   

- EN EL DOCUMENT.READY
 
var $inputCard = $('#card-number');
  var $inputMonth = $('.input-month');
  var $inputYear = $('.input-year');
  var $buttonNext = $('#next');
  var regexOnlyNumbers = /^[0-9]+$/;
  var labelErrorOrSuccessMessages = $('label[for="card-number"]');

- function soloNumeros(input):

var regex = /^[0-9]+$/;

- function isValidCreditCard(numberCard):

var creditCardNumber = soloNumeros(longitud(numberCard));
var arr = [];
var sumaTotal = 0;

- En los  ciclos  For:

var index