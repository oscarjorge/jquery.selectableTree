# JQuery Selectable Tree
jquery.selectabletree es un plugin de JQuery, fácilmente configurable, que despliega una serie de opciones opciones agrupadas que permiten seleccionar o no seleccionar los items desplegados. Trabaja con iconos de fontawesome.

![Texto alternativo](https://github.com/oscarjorge/jquery.selectableTree/blob/master/src/JQuery.selectableTree.JPG)


Puedes ver una desmostración del plugin [aquí](http://htmlpreview.github.io/?https://github.com/oscarjorge/jquery.selectableTree/blob/master/index.html)

## Parámetros

### Parámetros obligatorios:
#### dataSource: 
Son los datos que mostrará el árbol. Es un objeto JSON con la siguiente estructura:

* Children: Array de objetos Item
* Item: Propiedades de Item
  * Dirty: Indica si el elemento ha sido modificado por el cliente desde que se cargó por primera vez
  * Disabled: Establece si un elemento está deshabilitado o no
  * OriginalSelected: Establece si el elemento aparecerá o no seleccionado al cargar el ábol
  * Selected: Indica si el elemento está actualmente seleccionado
  * Text: Texto que aparece en el elemento
  * Value: Valor del elemento
  
### Parámetros opcionales:
#### colorInHeader (default:true): 
Pone un color de fondo en la cabecera de cada opción
#### collapsed (default:true): 
Establece si las opciones padre aparecerán collapsadas o desplegadas al cargar el componente
#### iconCollapsed (default:fa-angle-up): 
Icono de fontawesome que aparece cuando una opción padre está collapsada
#### iconUncollapsed (default:fa-angle-down): 
Icono de fontawesome que aparece cuando una opción padre está desplegada
#### iconChecked (default:fa-circle): 
Icono de fontawesome que aparece cuando una opción está seleccionada
#### iconUnchecked (default:fa-circle-o): 
Icono de fontawesome que aparece cuando una opción no está seleccionada
#### iconMixchecked (default:fa-circle-thin): 
Icono de fontawesome que aparece cuando una opción padre tiene hijos seleccionado y no seleccionados

## Eventos
#### onCheck
Es disparado cuando un elemento es seleccionado o cuando un elemento se deselecciona. El evento recibe un parámetro de tipo Item que representa la opción que ha disparado el evento.

# Getting Started

## Incluir los archivos necesarios
```html
<script src="https://code.jquery.com/jquery-1.12.4.min.js"></script>
<script src="js/jquery.selectableTree.js"></script>
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
<link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet" integrity="sha384-wvfXpqpZZVQGK6TAh5PVlGOfQNHSoD2xbE+QkPxCAFlNEevoEH3Sl0sibVcOQVnN" crossorigin="anonymous">
<link rel="stylesheet" type="text/css" href="css/jquery.selectableTree.css">
```
## Instanciar el plugin
```html
//Fuente de datos del arbol
var json = '[{"Item":{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"B�vidos","Value":"01","Dirty":false},"Children":[{"Disabled":false,"OriginalSelected":true,"Selected":true,"Text":"B�vidos","Value":"01","Dirty":false}]},{"Item":{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"�quidos","Value":"04","Dirty":false},"Children":[{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Asno","Value":"51","Dirty":false},{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Burd�gano","Value":"50","Dirty":false},{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Caballo","Value":"48","Dirty":false},{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Cebra","Value":"52","Dirty":false},{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Mulo","Value":"49","Dirty":false},{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Onagro","Value":"53","Dirty":false}]},{"Item":{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Peque�os Rumiantes","Value":"03","Dirty":false},"Children":[{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Caprino","Value":"04","Dirty":false},{"Disabled":false,"OriginalSelected":false,"Selected":false,"Text":"Ovino","Value":"03","Dirty":false}]}]'
//Convertimos el array a un objeto JSON
var datos = JSON.parse(json);
//Instanciamos el plugin y nos subscribimos al evento onChange
$('#arbol').selectableTree({
    colorInHeader: true,
    collapsed: true,
    dataSource: datos,
    onCheck: function (e, item) {
    }
});
```
