====================
El Lenguaje GraCieLa
====================

¡Bienvenidos a la especificación del lenguaje **GraCieLa**! A continuación se mostrará la estructura de un programa en GraCieLa, además de las diferentes construcciones disponibles en **GraCieLa** para el programador. Las construcciones explicada aquí son básica, dejando la definición y uso de TADs (Tipos de Datos Abstractos) y apuntadores, para la siguiente sección.

-------------------------
Estructura de un programa
-------------------------

Todo programa en **GraCieLa** debe tener un nombre que lo identifique. Este nombre puede o no ser igual al nombre del archivo. El nombre del programa puede ser cualquier identificador válido (secuencia de letras y números, tal que el primer caractér es una letra y no corresponda con una palabra reservada).::

  program <Nombre del programa> begin
      <Declaración de funciones y procedimientos>
    |[
      <Declaración de constantes y variables>
      <Acciones del programa>
    |]
  end
  
Un programa en **GraCieLa** puede definir varias funciones y varios procedimientos (incluso ninguno). Además, puede declarar varias constantes y variables (incluso ninguna). Las acciones del programa en realidad corresponden a una sóla instrucción, ya sea esta simple (i.e. asignación, impresión), compuesta (i.e. secuenciación, selección) o incluso la instrucción de inacción ``skip``.

------------------
Bloques de alcance
------------------

Para crear un nuevo alcance, basta con encerrar el código entre ``|[`` y ``]|``. Este nuevo alcance incluye cualquier nombre que haya sido declarado en alcances circundantes. Es importante resaltar que no se permite la redeclaración de nombres dentro de alcances nuevos. Esto es, si una variable *a* está ya declarada y visible, será imposible declarar una nueva variable *a* en el nuevo alcance. Las variables de un alcance inferior no pueden ser vistas (utilizadas) en un alcance superior.

--------------
Tipos de datos
--------------

**GraCieLa** cuenta con un conjunto de tipos de datos, simples y compuestos, a disposición del programador.

^^^^^^^^^^^^^^^^^^^^^^
Tipos de datos simples
^^^^^^^^^^^^^^^^^^^^^^
 
Los tipos simples son aquellos tipos que no se construyen a partir de otros tipos. En **GraCieLa** esto corresponde a los tipos primitivos: booleanos, enteros, flotantes y caracteres.

"""""""""
Booleanos
"""""""""

Corresponde a los valores lógicos de comparación y son representados por las palabras reservadas ``true`` y ``false``. Se declaran utilizando la palabra reservada ``boolean``.

"""""""
Enteros
"""""""

Corresponde a los números enteros, pueden tomar valores positivos y negativos. Se declaran utilizando la palabra reservada ``int``. Ocupan 32 bits de memoria.

"""""""""
Flotantes
"""""""""

Corresponde a los números reales o punto flotantes **IEEE-754**, pueden tomar valores positivos y negativos que contengan parte decimal. Se declaran utilizando la palabra reservada ``double``. Ocupan 64 bits de memoria.

""""""""""
Caracteres
""""""""""

Corresponde a un carácter imprimibles de **ASCII**.  Se declaran utilizando la palabra reservada ``char``. Ocupan 8 bits de memoria.

^^^^^^^^^^^^^^^^^^^^^^^^^
Tipos de datos compuestos
^^^^^^^^^^^^^^^^^^^^^^^^^
 
Los tipos compuestos son aquellos que, en su concstrucción, dependen de un tipo base. En **GraCieLa**, sin contar la definción de TADs, los tipos compuestos son únicamente los arreglos.

"""""""""""""""""""""""""
Arreglos unidimensionales
"""""""""""""""""""""""""

Se declaran utilizando la palabra reservada ``array`` y tienen base cero (empiezan en cero). Son homogéneos, por lo que sólo pueden contener valores de un mismo tipo. Su ocupación en memoria corresponde a la anchura del tipo por el tamaño del arreglo. Los índices sólo pueden ser expresados usando valores enteros no negativos del tipo.

La declaración de un arreglo con *<Número>* elementos de tipo *<Tipo>* es la siguiente::

  array [<Número>] of <Tipo>;
  
""""""""""""""""""""""""""""
Arreglos multidimensionales
""""""""""""""""""""""""""""

Son similares a los arreglos unidimensionales, la diferencia siendo que se puede otorgar más de una dimensión al mismo. Cada una de estas dimensiones tiene base cero y es almacenada usando una estrategia *row-major*.

La declaración de un arreglo multidimensional con :math:`<Número_0> x <Número_1>` elementos de tipo *<Tipo>* es la siguiente::

  array [<Número_0>, <Número_1>] of <Tipo>;

Es importante notar que los tipos ``array [<Número_0>] of array [<Número_1>] of <Tipo>`` y ``array [<Número_0>, <Número_1>] of <Tipo>`` son tipos distintos. El primero representa a un arreglo unidimensional de *<Número_0>* arreglos unidimensionales, cada uno de *<Número_1>* valores de tipo *<Tipo>*. El segundo es un arreglo de dos dimensiones, siendo la primera *<Número_0>* y la segunda *<Número_1>*, de valores de tipo *<Tipo>*.
