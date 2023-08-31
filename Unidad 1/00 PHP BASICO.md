Inicializamos servicios de apache y mysql en xampp.

![[Pasted image 20230824072857.png]]

Abrimos la carpeta php básico en visual studio code y agregamos un archivo llamado index.php. 
Generamos una estructura html e insertamos código en php para imprimir un hola mundo.

![[Pasted image 20230824072817.png]]
Se pueden realizar impresiones con print y echo, agregando incluso estilo al texto escrito.
![[Pasted image 20230824073348.png]]

Las **variables en PHP** se declaran de forma automática, para saber el tipo de dato que tiene nuestra variable se utiliza var_dump.

![[Pasted image 20230824074547.png]]
Algunas de las *reglas para nombrar variables en PHP* son las siguientes:
1. Usar únicamente caracteres latinos (0-9,a-z,A,Z) y guion bajo.
2. No utilizar caracteres especiales
3. Si se puede utilizar guion bajo al comienzo del nombre de una variable.
4. Nombrar las variables con significado semántico.
5. Tener en cuenta que se distinguen entre nombres con mayúsculas y minúsculas. Ej. apellidoMaterno no es igual a apellidomaterno.
6. Evitar palabras reservadas.

La definición de constantes se hace con la función *define()*. Como *primer parámetro* el nombre de la **constante** y como *segundo parámetro* el **valor de la constante**.

Para imprimir variables usamos la concatenación y el **.**

![[Pasted image 20230824075807.png]]

### Operaciones aritméticas

![[Pasted image 20230824080257.png]]
![[Pasted image 20230824082950.png]]

### **Operaciones lógicas**

En **PHP** las operaciones lógicas son:

| nombre | símbolo |
|----------|----------|
| AND|&&|
|OR|![[Pasted image 20230824082240.png]]|
|NOT|!|

**Operadores de comparación**

![[Pasted image 20230824082813.png]]

## **IF ELSE**
La secuencia nos permite ejecutar un bloque de código si se cumple una condición.

Para usar if else lo hacemos de la siguiente manera:

```php
<?php

    $edad=60;

    if ($edad >= 18 and $edad <30){

        print("Eres mayor de edad");

    }elseif($edad >=30 and $edad <60){

        print("Eres un adulto joven");

    }elseif($edad >= 60){

        print("Eres un adulto mayor");

    }else {

        print("Eres menor de edad");

    }

?>
```

## Switch

La secuencia nos ayuda a evaluar una sentencia, si hace match con algún case se ejecuta hasta encontrar un break, como en la siguiente secuencia:

```php
<?php

    $opcion ="HTML";

    switch($opcion){

        case 'HTML':

            print("Lenguaje de maquetado");

            break;

        case 'CSS':

            print("Hojas de estilo");

            break;

        case 'JS':

            print("Lenguaje de programación cliente");

            break;

        default:

            print("No conozco ese lenguaje");

            break;

    }

?>
```

Si no hace match con ningún case se ejecuta el default.

## while

Nos permite *ejecutar un bloque de código siempre y cuando se cumpla una condición.** Tiene como característica **evaluar y después ejecutar.**
Se usa de la siguiente manera:

```php
<?php

  

    $a = 0;

    while ($a <=10){

        print($a);

        $a++;

    }

?>
```

## Do While

Una característica de do while es que **primero ejecuta y después evalúa.**

```php
<?php

    $a = 11;

    do {

        print($a);

        $a++;

    }while($a <=10);

?>
```
## Arreglos

Los arreglos pueden *combinar diferentes tipos de datos.*
En PHP se hacen de la siguiente forma:

```php
<?php

    $calificaciones = [100, 99, 89, 78,];

    $arreglo = ["Hola mundo", 24, true];

  

    echo "<pre>";

    print_r($calificaciones);

    echo "</pre>"; //preformatear estructuras

?>
```
## Objetos
Los *objetos* en **PHP** únicamente existen cuando son **instancias de una clase.**

### Arreglos asociativos

Se conforman por *clave - valor*, se definen:

```php
<?php

    $persona = [

        "nombre" => "Valeria",

        "edad" => 23,

        "direccion" => [

            "ciudad" => "CDMX",

            "alcaldia" => "Xochimilco",

            "pueblo" => "Santa Cruz"

        ],

        "calificaciones" =>[12,23,34,45,67,78],

    ];

    echo "<pre>";

    print_r($persona);

    print($persona["calificaciones"][3]);

    echo "</pre>";
?>
```
##  For
Nos permite *acceder e iterar* un arreglo mientras **una condición se cumpla.**
Ejemplo:

```php
<?php

    $calificaciones = [100, 99, 89, 78,];

    $arreglo = ["Hola mundo", 24, true];

    for($i=0; $i < count($calificaciones); $i++){

        print("iteracion: " .$i. " valor:".$calificaciones[$i]);

        print($calificaciones[$i]);

        echo "<br>";

    }

    for($i=0; $i < count($arreglo); $i++){

        print("iteracion: " .$i. " valor:".$arreglo[$i]);

        print($arreglo[$i]);

        echo "<br>";

    }

?>
```

### Foreach
Se usa de la siguiente manera:

```php
<?php

  $persona = [

    "nombre" => "Valeria",

    "edad" => 23,

    "direccion" => [

        "ciudad" => "CDMX",

        "alcaldia" => "Xochimilco",

        "pueblo" => "Santa Cruz"
    ],

    "calificaciones" => [12,23,34,45,67,78],
];

  $calificaciones = [100, 99, 89, 78,];

  $arreglo = ["Hola mundo", 24, true];

  /* foreach($calificaciones as $calificacion){

    print($calificacion);

    echo "<br>";

  }

  foreach($calificaciones as $calificacion):

    print($calificacion);

    echo "<br>";

  endforeach; */ //shift + alt + A
  foreach($persona as $llave => $valor){

    /* print_r("Llave: " .$llave. " valor: " .$valor);

    echo "<br>"; */

    print(gettype($valor));

    echo "<br>";

  }

?>
```
## Funciones
Nos permiten realizar acciones de manera independiente
*Ejemplo:*
```php
<?php
    function saludar($nombre,$apellido){
        return "Hola ". $nombre." ".$apellido;
    }
    print(saludar("Valeria","Aguilar"));
?>
```
## Clases 
Nos permite **organizar el código,** se pueden utilizar de la siguiente manera:
```php
<?php

    class Persona {
        public function __construct(public $nombre, public $apellido, public $edad) {}

    }

    class Alumno{
        public $matricula;
        public $nombre;
        public $apellido;
        public $edad;

        public function __construct($matricula, $nombre, $apellido, $edad) {
            $this->matricula=$matricula;
            $this->nombre=$nombre;
            $this->apellido=$apellido;
            $this->edad=$edad;

        }
        
        public function reprobar($materia){
            return "Reprobaste: " .$materia;

        }

        public function aprobar($materia, $calificacion){
            return "Aprobaste: " .$materia. " con: " . $calificacion;

        }
    }

    $nombre = new Persona ("Valeria", "Aguilar",23);
    $alumno = new Alumno(201190040,"Valeria","Aguilar",23);

    echo "<pre>";
    print_r($nombre);
    print_r($alumno);
    print($alumno->aprobar("POO",70));
    print($alumno->reprobar("POO",50));
    echo "</pre>";

?>
```

## Encapsulamiento
Los métodos estáticos no pueden hacer referencia a propiedades de ese objeto.
```php
    class Producto{
        public function __construct(protected $nombre = "Oreo", private $precio = 29, protected $caducidad = "29/09/2023") {}
        static public function obtenerProducto(){

            return "Accedimos al metodo estatico";
        }
    }
    $galletas = new Producto("Principe", 20, "29/09/2023");

```

Para acceder a un método estático se usa *::*
```php
print_r(Producto::obtenerProducto());
```

