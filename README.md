# Aprender PHP desde cero hasta profesional
Bienvenidos a mi manual completo con todos los recursos necesarios para aprender php desde cero hasta una profesional de una manera cool y facil sin problema, espero que te guste y lo compartas.


 primero yo estoy usando la version 5 de php para este manual pero vere cosas de php 7 y versiones anteriores que es necesaria saber en php funcional.
 
  primero deberias tener un servidor web local para hacer test, yo te recomiendo usar XAMPP es el mas facil pero si usas Windows posiblemente te de problemas pero si es bueno y si usas linux te recomiendo instalar sencillamente LAMP y listo.
  
  
   los comandos para instalar LAMP en este caso ubuntu son:
    
    necesitas permisos root para esto.

   primero instalamos apache:
   
   sudo apt install apache2
   
todo el mundo conoce apache actualmente esta en la version 2.4 (2018), pero bueno si no sabes que es Apache no te preocupes aqui te         explicare lo que es:

Apache es un servidor web HTTP de código abierto para plataformas Unix-like (BSD, GNU/Linux, etc.), Windows, Macintosh y otras, que implementa el protocolo HTTP/1.1 y la noción de sitio virtual. En sus inicios se basaba en el código de NCSA HTTPd 1.3, pero más tarde fue reescrito por completo.

aunque existen mas servidores web el mas popular es apache(bueno principalnente porque es open source y aquien no le gusta el open source y lo gratis)


fuente:https://clientes.hostname.cl/knowledgebase.php?action=displayarticle&id=35


instalamos mySQl:

sudo apt install mysql-server


despues instalamos PHP

sudo apt install php-pear php-fpm php-dev php-zip php-curl php-xmlrpc php-gd php-mysql php-mbstring php-xml libapache2-mod-php


 ya despues le das resert a apache (si estas en linux) con el siguiente comando:
 
 sudo service apache2 restart
 
 
 despues entras a esta URL: http://localhost/
 
  si no sabes que es localhost:
  
  "Localhost" se refiere  a la tu local en tu computadora  por ejemplo, si estas usando tu navegador,tu computadora es considera  "localhost.", sencillamente es es parte local de tu misma computadora la cual puedes usarla como un servidor web pero sin salida a internet, igualmente es usada en redes de computadoras para hacer ping a ti mismo para hacer test de red y todo un show pero ese no es el tema de este manual.
  
  fuente:https://www.quora.com/What-is-a-local-host


 en windows no es necesario solo abres el control de XAMPP desde el menu buscando xampp
 
 
 fuente:https://howtoubuntu.org/how-to-install-lamp-on-ubuntu
   
   
   
 ################ ################ ################ ################ ################ ################

Ahora que ya tienes tu servidor instalado y corriendo vamos a ver PHP pero que es PHP:


como dice wikipedia PHP  es:

PHP: Hypertext Preprocessor (or simply PHP) is a server-side scripting language designed for Web development, but also used as a general-purpose programming language. 

sencillamente un lenguage de programacion orientadl a scripting, si no sabes lo que son los lenguages script te recomiend googlear sobre ellos antes de continuar con este manual.


soporta: diferentes tipo de programacion que son:	Imperative, functional, object-oriented, procedural, reflective


en este manual veremos solamente funcional y POO.

su creador es: Rasmus Lerdorf

fuente:https://en.wikipedia.org/wiki/PHP

bueno ya que sabemos que onda con PHP y que es vamos empezemos a programar algunos simples script php para que aprendas la sintaxis 
facil de PHP.


 supongo yo que tienes  instalado un editor de codigo como sublime text 3 que en este caso.
 
 primero debes crear una carpeta llamada nose aprender-PHP en tu servidor web xampp/LAMP para windows solo busca en tu disco local la carpeta xampp/htdocs
 
 y ahi crea una carpeta con el nombre que quieres posiblemente te pida permiso de administrador bueno en linux es algo similar solo que tienes que ir  var/www/html (depende de tu version)
 
 continuemos:
 
  lo primero que debes aprender en PHP es como se inicie PHP cuando creas un sitio web:
  
  antes de esto debes crear un archivo llamado index.php y agregar una simple estructura html
  
  Cuando PHP se agregara en el codigo html se utilizan las tangs :   <?php y  ?>  (las debes agregar dentro del body)   las cuales le estan indicando al servidor web apche en este caso que este sitio tiene una peticion PHP y  debe ejuctarla con el compilador de PHP que mas adelante veremos como funciona y como jugar con el.
  
  aunque existen otras maneras de agregar estas etiquetas las mas usadas son estas.
  
  fuente:http://php.net/manual/en/language.basic-syntax.phptags.php
  
  
  despues de iniciar PHP en tu codigo html, debes conocer como los tipos de datos  en php en todos los lenguages existen las tipos de datos y sirven para lo mismo, pero claro la declaracion cambia un poco en cada lenguage como en javascript,java,ruby,python igual en       php pero no cambia mucho y se entiende rapidamente.
  
  bueno en PHP actualmente existen:
  
  booleano
  integers (int)
  float (un punto flotante)
  Strins (cadena)
  Arrays
  iterables
  Objects
  Resources
  NULL
  Callbacks 
  
  
   primero veremos booleanos , como funciona y  como se declara:
   
   bueno como sabes un boleano solo puede devolver dos valores un TRUE o FALSE (osea un verdadero o falso)
   
   y se declara de la siguiente manera:
   

<?php
$humano = True; // asignamos el valor True a la variable humano
?>
  
  existen maneras de hacer algunos test sencillos donde se usa los booleanos, como por ejemplo en el siguiente codigo:
  
  // == es un operador que te permite saber si es true una variable en este caso el string.
if ($action == "show_version") {
    echo "esta disponible";
}

//igualmente existe una manera de saber si algo es true, de la siguiente manera, pero es inutil usar un TRUE dentro de un if porque //todo los if en todos los lenguages funciona igual, si pasas una variable,etc en un if el valor debe ser true sino se pasa al else
//por eso es inutil usar un TRUE dentro del if.

if ($show_separators == TRUE) {
    echo "<hr>\n";
}
  
  NOTA importante:-1 es considerado TRUE.
  
  Ahora que ya sabes como funciona los booleanos en php , pero para que los podria usar en mis proyectos web bueno sencillamente en   muchas cosas los puedes usar por ejemplo en sesiones de usuarios en un sistema web,en una validacion cuando  agregas un dato en bd,para saber si existe algun valor o no,etc.

bueno ahora veremos el intergs que literalamente es el INT en PHP.


intergs puede ser especificado en decimal (base 10) , hexadecimal (base 16), octal (base 8) o binary (base 2)



 NOTA: Binary integer literals esta disponible desde la version  PHP 5.4.0.
 
   bueno y como se declaran, de la siguiente manera:
   
   
<?php
$a = 1234; //numero  decimal 
$a = -123; // un numero negativo
$a = 0123; // numero octal  (equivalente  a 83 decimal)
$a = 0x1A; //numero  hexadecimal  (equivalente a 26 decimal)
$a = 0b11111111; //  numero binary  (equivalente a 255 decimal)
?>

 La dimension de un  integer es dependiente de la plantaforma, el tamaño puede ser determinado usando la constante PHP_INT_SIZE, maximo valor usando la constante  PHP_INT_MAX since PHP 5.0.5, y el minimo valor usando la constante PHP_INT_MIN since PHP 7.0.0. 
 
 los integer son usados en PHP con los Arrays puees hacer muchas cosas con ellos.
 
 
 
 Bueno ahora que ya conoces sobre los intergs deberias conocer los float o llamado comunmente doblues.
 
<?php
$a = 1.234; 
$b = 1.2e3; 
$c = 7E-10;
?>

Igual como con el intergs los float son dependiente de la plantaforma para su tamaño.


los numeros flotantes tienen un limite de precision.JQuery depente del sistema operativo, PHP usa tipicante  IEEE 754 format

si quieres aprender mas sobre este formato te sugiero leer este articulo en ingles: http://www.oxfordmathcenter.com/drupal7/node/43


Ahora que  conoces que es y como funciona un float ahora vamos a ver como fuciona el Strings:

una cadena es una serie de caracteres, donde un carácter es lo mismo que un byte. Esto significa que PHP solo admite un conjunto de 256 caracteres y, por lo tanto, no ofrece compatibilidad nativa con Unicode. Ver detalles del tipo de cadena

los string en PHP se declaran de diferentes maneras:

ingle quoted
 un ejemplo:

echo 'Hola';

double quoted

un ejemplo:
<?php
echo "Hola";

heredoc syntax
un ejemplo:

$mensaje = <<<EOD  
Hola
EOD;

 nowdoc syntax (agregada en PHP 5.3.0) 
$str = <<<'EOD'
Hola
EOD;

Ahora que ya conoces lo mas basico sobre los strings lo cual esta bien por el momento, ahora veremos como funcionan los Arrays en PHP, si conoces los Arrays porque los aprendistes en otros lenguages como Java o JavaScript,etc, ps no cambia mucho su funcionalidad en PHP.

como sabemos un array es un conjunto de datos ordenados sencillamente.

y se puede declarar con la funcion  array() de php de la siguiente manera:

array(
    key  => value,
    key2 => value2,
    key3 => value3,
    
)

debes saber que en php puede omitir la ultima coma en el ultimo valor.


desde php 5.4 puedes remplazar la funcion array() con [] y crear arrays mas faciles de la siguiente manera:

$array = [
    "valor1" => "maria",
    "valor2" => "juan",
];

debes saber que en un array php la claves o mejor llamada keys pueden ser un string que contenga un interg,float,booleanos  pero un array y objecto no puede ser keys en los arrays en PHP si lo intentas te mostraria el siguiente error o alerta mejor dicho: 

 Illegal offset type. 
 si  tienes multiples valores con el mismo tipo de keys  solo el ultimo srea el validos y los otros seran sobre escrito.
 
 por ejemplo si tuvieramos el siguiente codigo:
 
 
 
<?php
$array = array(
    1    => "a",
    "1"  => "b",
    1.5  => "c",
    true => "d",
);
var_dump($array);
?>

y yo quiero imprmir el primer 1 que su valor es a,el resultado no seria a seria b.

siendo honesto eso no me gusta de PHP que tenga esto no conozco otra manera de hacerlo aunque buscare de existe y lo agregare.

debes saber que en php existen los arrays sin keys y se crean de la siguiente manera:


<?php
$array = array("valor1", "valor2", "valor3", "valor4");
var_dump($array);
?>

 si tienen un indentificador pero no como los arrays anteriores.

en php puedes especificar solo un keys y a los otros no de la siguiente manera:



<?php
$array = array(
         "a",
         "b",
    6 => "c",
         "d",
);
var_dump($array);
?>

aunque a mi se me hace raro porque vengo de java pero php lo tiene y deberias saberlos.

ahora que ya conoces lo mas importante sobre los arrays ahora veremos como acceder  a ellos.


okay ahora imaginemos que tenemos este array multidimensional:

$array = array(
    "foo" => "bar",
    42    => 24,
    "multi" => array(
         "dimensional" => array(
             "array" => "foo"
         )
    )
);

por ejemplo si quieres acceder al valor de foo sencillamente debes hacer algo asi:

var_dump($array["foo"]);


y lo veras en la pantalla su valor.

pero ahora imaginemos que quieres acceder al valor array de multi, deberias hacer algo asi:

var_dump($array["multi"]["dimensional"]["array"]);


asi de  sencillamente  ya accedistes al valor de multi.


ahora vamos a ver sobre Array dereferencing , es saber un valor de un array desde una funciona, lose algo raro y complicado pero con el siguiente ejmplo lo entenderas mejor.


  okay imaginemos que tienes esta funcion:
  
  function ObtenerArray() {
    return array(1, 2, 3);
}

como vez tenemos un array con los siguientes valores  y si quieres obtener un valor del array deberias hacer algo asi:

// en la version de PHP 5.4
$segundoelemento = ObtenerArray()[1];

como vez en el codigo crea una variable llamada $segundoelemento el cual indicamos la funcion obtenerArray y indicamos el indice 1 del  array el cual es el valor 2 en el array.

y conb un echo podrias imprimirla.

ahora que ya conoces como funciona un array a nivel basico deberias conocer la funcion
unset() de PHP que es muy interesante y buena, a continuacion veremos algunos ejemplos basicos con esta funcion:

 pero antes de nada deberias saber como agregar un nuevo elemento en un array.
 
 $arr["x"] = 42; //agregas el valor 42 con el key x en el array llamado arr
 
  okay ahora que ya sabes como se agrega un nuevo elemento al array deberias saber
  como se elemina un elemento,imaginemos que quieres eliminar el elemento 5 en un array deberias  hacerlo de la siguiente manera :
 
               
unset($arr[5]); // Esto elemina el elemento 5 en el array arr

pero si quieres por ejemplo eleminar todo el array deberias hacer algo asi:

unset($arr);

Resources

 Un Resources es una variable especial que contiene una referencia a un recurso externo. Los recursos son creados y utilizados por funciones especiales.
 
 para devolver algo podrias usar la funcion  get_resource_type agrega en la version: (PHP 4 >= 4.0.2, PHP 5, PHP 7)
 
 su estructura es asi:  string get_resource_type ( resource $handle )
 
   $handle es el valor que devolvera.
   
   un ejmeplo sencillo para este tipo de datos es este:
   
   // imprimir: mysql link
    $c = mysql_connect();
   echo get_resource_type($c) . "\n";
   
   imaginemos que queremos imprimir el link de la conexion de $c  otros ejemplos es por ejemplo si quieres imprimir un documento        
   o un archivo xml.
   
   Ahora que ya conocer el recources deberias conocer el tipo NULL
   
   
   bueno como ya conoces y todo el mundo que ya tiene un minimo conocimiento de programacion debe saber que los tipo null 
   siginifca nada es un tipo de valor que no contiene nada.
   
   un ejemplo es este:
   
   
    <?php 
    $var = NULL;       
    ?>


     bueno ahora que ya conoces el tipo de valor NULL deberias ver los objectos en PHP.
     
     
     bueno si sabes  algo de POO sabras que un objeto es sencillamente algo de la vida real en la programacion por ejemplo si 
     tenemos un carro el carro es el objeto y sus caracterizticas son las propiedades del ojetos y la  cual seran usadas por 
     metodos para hacer algo en este caso seran las funcionalidades que el carro hara.
     
     
     pero como se crear el objeto ps de la siguiente manera:
     
     
   <?php
class MyClase
{
    function Haceralgo()
    {
        echo "mensaje "; 
    }
}

    $bar = new MyClase;
    $bar->Haceralgo();
   ?>
    bueno expliquemos el codigo anterior cree una clase llamada MyClase la cual es el molde para los objetos y metodos
    despues cree un sencillo metodo/funcion el cual devuelve un string con un mensaje, mas abajo cree una variable llamada $bar
    la cual esl a instancia del objeto creado en seguida de $bar esta new la cual crea un objecto de la clase MyClase
    y despues usando ese objeto llamado al metodo Haceralgo para imprimir el mensaje.
    
    como vez es sencillo crear objectos y usarlos de una manera sencilla y sin complicaciones.
    
    
    Ahora que ya conoces los objetos deberias ver los Iterables que es algo casi nuevo en PHP se agrego en la version de php 7.1
    
    Iterable es un pseudo-tipo introducido en PHP 7.1. Acepta cualquier matriz u objeto que implemente la interfaz de 
    Traversable. Ambos tipos son iterables utilizando foreach y se pueden usar con rendimiento desde dentro de un generador.
    
    buenos los Iterables no son muy usados en mi punto personal casi no los veo pero  si quieres conocer te recomiendo leer esto 
    en ingles :
    
       
       [info sobre los Iterables](http://php.net/manual/en/language.types.iterable.php)
       
       
       Ahora que ya conoces la mayoria de los tipo de datos te falta conocer solamente el ultimo que es :
       
       
       Callbacks / Callables 
              [Callbacks / Callables](https://stackoverflow.com/questions/48947/how-do-i-implement-a-callback-in-php)

Ahora que ya conoces los tipos en php deberias conocer las variables en PHP, bueno como todo el mundo sabe las variables son 
cambo en memoria que almacena un dato temporalmente.

en php las variables son representadas por un simbolo de dolar primero y despues el nombre, de esta manera:

    $Nombre = 'Bob';
    
      Variables  predeterminadas:
      
      PHP tiene un conjunto de variables definidas en el lenguaje de programacion PHP.
      
      Superglobals :
      
      los superglobales son variables integradas que están siempre disponibles en todos los ámbitos.
      
      Varias variables predefinidas en PHP son "superglobales", lo que significa que están disponibles 
      en todos los ámbitos a lo largo de un guión. No hay necesidad de hacer global $ variable; 
      para acceder a ellos dentro de funciones o métodos.
      
      
      Estas variables superglobales son:
      
    $GLOBALS  :
    
    $_SERVER  :
     obtener información del servidor y del entorno de ejecución
      

    
    $_GET     :
    
    $_POST    :
    
    $_FILES   :
    
    $_COOKIE  :
    
    $_SESSION :
    
    $_REQUEST :
    
    $_ENV     :

       
    
    



   
    
    
   
   


  
 
 


 




