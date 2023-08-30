### hola mundo 
para iniciar los servicion en mamp o xamp 

![[Captura de pantalla 2023-08-24 a la(s) 7.22.52.png]]

crear una carpeta en htdocs

![[Captura de pantalla 2023-08-24 a la(s) 7.24.35.png]]

dentro de visual estudio code creamos un archivo index.php con estructura basica de html 

```html
<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Document</title>
</head>
<body>

</body>
</html>
```

agregar un tag de php 

```php 
<!DOCTYPE html>

<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>
	<?php
		print("hola mundo");
	?>
	</body>
</html>
```

otras pociones para escrivir en php son las siguientes 

```php
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>
	<?php
		print("hola mundo");
		echo "<br>";
		echo "<h1>hola mundo</h1>";
	?>
</body>
</html>
```

los comentarios se utilizan asi "//"

## variables y su uso

var _domp nos muestra el tipo de variable 

las variables en php se declaran con el signo de $
 ```php
<?php
	
	$nombre = "Axel";
	$edad = 29;
	$mayor_edad = true;
	var_dump($nombre);
	var_dump($edad);
	var_dump($mayor_edad);

?>
 ```


#### algunar reglas de nombres de variable en php

1-usar unicamente caracteres latinos (0-9,a-z,A-Z) y guion bajo
2-no utilizar caracteres especiales 
3-si se puede utilisar el guion bajo al comienso del nombre de la variable 
4-nombre de la variable con significado semantico 
5-tener en cuenta que se distinga entre nombres con mayuscula y minuscila 
6-evitar palabras reservadas 


le definicion de variables se ase con la fincion define() comp primer parametro el nombre de la constante y luego su valor de dicha constante 

```php
<?php

	$nombre = "Axel";
	
	$edad = 29;
	$mayor_edad = true;
	var_dump($nombre);
	var_dump($edad);
	var_dump($mayor_edad);
	
	define("pi",3.1516);//con esta manera podemos declarar constanten en php
	print("mi nombre en: " . $nombre);//la concatenacion se ase con .	
	print(" la constante pi es: " . pi);

?>
```

### operaciones aritmeticas

las operaciones aritmeticas no son diferentes de otros lenguajes 

```php 
<?php

	print(5+4); //suma
	print(5-4); //resta
	print(5*4); //multiplicacion
	print(5/4); //divicion
	print(10%2); //modulo
	print(2**2); //potencia

?>
```

## opreraciones lógicas 
las operaciones loguicas son las siguientes 

| nombre | simbolo |
|--------|---------|
| and    | && o and|
| or     | or o ll |
|not     | !       |

![[Captura de pantalla 2023-08-24 a la(s) 8.25.56.png]]
## if  y ifelse

la sentencio if nos permite ejecutar un bloqué de código si una condición se cumple 
if else se ejecuta cuando no se cumple 
```php 
<?php

	$edad = 60;
	if ($edad >= 18 and $edad < 30) {
	print("Eres mayor de edad");
	}else if($edad >= 30 and $edad < 60) {
	print("Eres un chavo ruco");
	}else if($edad >= 60) {
	print("Eres un adulto mayor");
	} else {
	print("Eres menor de edad");
	}
?>
```
## swich

nos ayuda a evaluar una opcion y no s ayuda a encontrar una setencio y si no ase mach con ningun case se ejecuta el default

```php 
<?php

$opcion= "js";

	switch ($opcion) {
		case 'html':
		print("Lenguaje de maquetado");
	break;
		case 'css':
		print("Hojas de estilos");
	break;
		case 'js':
		print("Lenjuague de programacion cliente");
	break;
		default:
		print("No conosco el lenguaje");
	break;
}
?>
```

## while 

nos permite ejecutar blockes de codigo siempre y cuando una condicion se cumpla una caracteristica es evaluar y despues lo compara 
```php
<?php
	
	$a= 0;
	
	while ($a <= 10) {
	print($a);
	$a++;
}
?>
```
## do while

la expresión de verdad se verifica al final de cada iteración en lugar de al principio.

```php 
<?php

$a= 0;

do {
print($a);
$a++
} while ($a <= 10);

?>
```

## arreglos

los areglos se asen de la siguiente forma 

```php 
<?php
	
	$calificaciones= [100,99,89,78,67,78];
	$arreglo =["hola mindo", 24, true];
	echo "<pre>";
	print_r($calificaciones);
	echo "</pre>";

?>
```
los arlegos pueden contener todo tipo de datos sin ningun problema 

## objetos

en php se llaman arreglos asociativos y son asi 

```php 
<?php

	$persona= [
		"nombre"=>"Axel",
		"edad"=> 29,
		"direccion"=> [
		"ciudad"=> "Milpa Alta",
		"pueblo"=> "San Juan"
		],
		"calificacion"=>[12,23,34,45,67,78]
		];
	
	echo "<pre>";
	print_r($persona);
	print($persona["nombre"]);
	print($persona["direccion"]["nombre"]);
	print($persona["calificaciones"][3]);
	echo "</pre>";

?>
```


## for
es una estructura que nos permite interar mientras una se cumpla 

```php
<?php
$calificacion = [12,23,34,45,67,78];
$arreglo =["hola mindo", 24, true];

for ($i=0; $i <count($calificacion) ; $i++) {
print("interacion: " .$i." valor ". $calificacion[$i]);
echo "<br>";
}

echo "<br>";
for ($i=0; $i <count($arreglo) ; $i++) {
print("interacion: " .$i." valor ". $arreglo[$i]);
echo "<br>";
}

?>
```
## foreach

unciona sólo sobre arrays y objetos, y emitirá un error al intentar usarlo con una variable de un tipo diferente de datos o una variable no inicializada.

```php
<?php
	$persona= [
		"nombre"=>"Axel",
		"edad"=> 29,
		"direccion"=> [
		"ciudad"=> "Milpa Alta",
		"pueblo"=> "San Juan"
		],
		"calificacion"=>[12,23,34,45,67,78]
	];
	$calificaciones = [12,23,34,45,67,78];
	$arreglo =["hola mindo", 24, true];
	
	foreach ($calificaciones as $calificacion ) {
		print($calificacion);
		echo"<br>";
	}
	/*foreach ($calificaciones as $calificacion ) :
	print($calificacion);
	echo"<br>";
	endforeach;*/
	foreach ($persona as $key => $value) {
		print("llave: ". $key. " valor: ". $value);
		print(gettype($value));
		echo "<br>";
	}
?>
```


## funciones

las funciones sirven para resolver una tarea 

```php 

<?php
  
function saludar($nombre,$apellido) {
	return "hola ". $nombre . " " . $apellido;
	}

print(saludar("Axel","Vertiz"));

?>

```
## calses

es una palabra reservada que puede guardar funciones y variables estas puedes ser publicas o privadas  

```php
<?php

class persona{
	public function _construct(public $nombre, public $apellido, public $edad);
}

class Alumno{
	public $matricula;
	public $nombre:
	public $apellido;
	public $edad;
	
	public function _construct($matricula, $nombre, $apellido, $edad){
		$this -> matricula = $matricula;
		$this -> nombre = $nombre;
		$this -> apellido = $apellido;
		$this -> edad = $edad;
	}
	  
	public function reprobar($materia){
		return "reprobaste: " . $materia;
		}
	public function aprobar($materia,$calificacion){
		return "aprobaste: " . $materia. "con: " . $calificacion;
		}
}

$alumno = new Alumno(201190021,"Axel","Martinez",20)
$parker = new persona("Axel","Martinez", 20);

echo "<pre>";
print_r($parker);
print_r($alumno);
print($alumno ->aprobar ("POO",70));
echo "<br>";
print($alumno ->reprobar ("POO"));
echo "</pre>";

?>
```

## Encapsulamiento

sirve para manipular y gestionar el acceso a los datos de la classe 

```php
<?php
  
class producto {
		public function __construct(protected $nombre = "Oreo",private $precio = 29,protected $caducidad = "29/09/2023"){}
		  
		public static function obtenerProducto(){
		return "accedimos al metodo estatico";
		/**
		* if ($nombre === $this->nombre) {
		* return "priducto: " . $this->nombre ."precio: " . $this-> precio        ."Caducidad: " . $this-> caducidad;
		* }else {
		* return "El producto no existe";
		* }
		*/
	}
}
$galletas = new producto("Principe",20,"29/09/2023");
  
echo "<pre>";
print_r($galletas->obtenerProducto("marias"));
echo "<br>";
print_r($galletas->obtenerProducto("Principe"));
echo "<br>";
print_r(producto::obtenerProducto("Principe"));
echo "</pre>";

?>
```


