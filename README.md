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

aunque existen mas servidores web el mas popular es apache(bueno principalnente porque es open source y aqui no le gusta el open source y lo gratis)


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

sencillamente un lenguage de progrmacion orienta a scripting, si no sabes lo que son los lenguages script te recomiend googlear sobre ellos antes de continuar con este manual.


soporta: diferentes tipo de programacion que son:	Imperative, functional, object-oriented, procedural, reflective


en eeste manual veremos solamente funcional y POO.

su creador es: Rasmus Lerdorf

fuente:https://en.wikipedia.org/wiki/PHP

bueno ya que sabemos que onda con PHP y que es vamos empezemos  programar algunos simples script php para que aprendas la sintaxis 
facil de PHP.


 supongoo yo que tienes ya instalado un editor de codigo como sublime text 3 que en este caso usare.
 
 primero debes crear una carpeta llamada nose aprender-PHP en tu servidor web xampp/LAMP para windows solo busca en tu disco local la carpeta xampp/htdocs
 
 y ahi crea una carpeta con el nombre que quieres posiblemente te pida permiso de administrador bueno en linux es algo similar solo que tienes que ir  var/www/html (depende de tu version)
 
 continuemos:
 
  lo primero que debes aprender en PHP es como se inicie PHP cuando creas un sitio web:
  
  antes de esto debes crear un archivo llamado index.php y agregar una simple estructura html
  
  Cuando PHP se agregara en el codigo html se utilizan las tangs :   <?php y  ?>  (las debes agregar dentro del body)   las cuales le estan indicando al servidor web apche en este caso que ste sitio tiene una peticion PHP y  debe ejuctarla con el compilador de PHP que mas adelante veremos como funciona y como jugar con el.
  
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
  Callbacks / Callables
  
  
   primero veremos booleano , como funciona y  como se declara:
   
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

//igualmente existe una manera de saber si algo es true, de la siguiente manera, pero es inutil usar un TRUE dentro de un if porque //todo los if en todos los lenguages funciona igual, si pasas una variable,etc en un if el valor debe ser true sino se pasa al esle
//por eso es inutil usar un TRUE dentro del if.

if ($show_separators == TRUE) {
    echo "<hr>\n";
}
  
  NOTA importante:-1 es considerado TRUE.
  
  Ahora que ya sabes como funciona los booleanos en php , pero para que los podria usar en mis proyectos web bueno sencillamente en   muchas cosas los puedes usar por ejemplo en sesiones de usuarios en un sistema web,en una validacion cuando  agregas un dato en bd,para saber si existe algun valor o no,etc.

bueno ahora veremos el intergs que literlamente es el INT en PHP.


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

 La dimension de un  integer es dependiente de la plantaforma, el tamaño puede ser determinado usando la constante PHP_INT_SIZE, maximo valor usando la constante  PHP_INT_MAX since PHP 5.0.5, and el minimo valor usando la constante PHP_INT_MIN since PHP 7.0.0. 
 
 los integer son usados en PHP con los Arrays puees hacer muchas cosas con ellos.
 
 
 
 Bueno ahora que ya conoces sobre los intergs deberias conocer los float o llamado comunmente doblues.
 
<?php
$a = 1.234; 
$b = 1.2e3; 
$c = 7E-10;
?>

Igual como con el intergs los float son dependiente de la plantaforma para su tamaño.


los numeros flotantes tienen un limite de precision.depente del sistema operativo, PHP usa tipucante  IEEE 754 format

si quieres aprender mas sobre este formato te sugiero leer este articulo en ingles: http://www.oxfordmathcenter.com/drupal7/node/43


Ahora que  conoces que es y como funciona un float ahora vamos a ver como fuciona el Strings:

 a string is series of characters, where a character is the same as a byte. This means that PHP only supports a 256-character set, and hence does not offer native Unicode support. See details of the string type. 

 
 




