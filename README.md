# AddressBook

Reporte

1.	Se inicia creando la clase AdrressBook.
2.	Se realiza la importación de la siguiente librería a utilizar (BufferedReader, BufferedWriter, FileReader, FileWriter, HashMap, Map y Scanner)
3.	Se crean las variables conts Maps<String, String> y la variable filePath String.
4.	En el método publico AdrressBook(String se utiliza el filePath en el cual se crean los métodos this de cada variable.
5.	Procedemos a realizar el método load utilizando un try catch, es donde se utiliza el BufferedReader y el FileReader y por último el filePatch(varible).
6.	Se utiliza un while en el cual se está indicando si la variable línea es igual a la variable del BufferedReader o si es diferente a vacío, si es null envía mensaje de Error de carga de datos del 
7.	En caso contrario utilizando dentro de lo anterior mencionado un if con la función de objetos length, el cual cuenta con un contenedor inicializado en cero en el numTel y uno en el nom, con el put permite almacenar los datos ingresados de cada variable, enviando el mensaje de Datos del contacto exitosos.  
8.	Se realiza un método de almacenamiento de datos es algo similar al anterior solo que el numTel es el getKey() el método el keycode es recuperado desde el arreglo keymap, en lo que el nom cuenta con un getValue, el cual devuelve el valor de propiedad de un objeto especificado con valores de índice opcionales para las propiedades indizadas.
9.	En caso de ser correcto el try se enviará el mensaje de contacto almacenado exitosamente y en lugar de un if se genera en un for.
10.	En caso contrario el catch enviara el mensaje Error de almacenamiento del contacto.
11.	Se crea el método list el cual almacenara una lista de los contactos por lo cual se utiliza un for en el cual se coloca un Map.Emtry para almacenar el valor de la variable con el String el entry esto cuenta con la variable en mi caso es conts,
12.	El numTel cuenta con el entry .getKey el cual se usa para obtener la clave asociada con el alias proporcionado(conts).
13.	Mostrando la lista de las variables numTel u nom.
14.	Método crear
15.	En este caso se utiliza un put el cual se encarga de asociar el valor con la clave en el mapa.
16.	Método eliminar
17.	Va asociado con una a condicionante if colocando la variable un containsKey la está ligada a numTel este método va a verificar si la clave está asignada al HasMap o no.
18.	Se coloca la variable acompañada con un remove el cual eliminara el elemento el cual se haga mención en el Objeto en mi caso (numTel), el cual si existe el contacto mostrara el mensaje de contacto eliminado o en caso contrario mostrara el mensaje del contacto no existe.
19.	Método menú
20.	Se realiza una variable con Scanner y un variable bolean.
21.	El método while donde se expone el menú deseado para realizar la elección de una opción a través de la variable int op dado a que es igual al scanner punto nextInt y la variable del scanner punto nexline para una línea siguiente.
22.	Para que la variable pueda funcionar debe de ser a través de un switch entre unos case en este caso son 5 case los cuales son:
23.	Case 1: manda llamar el método de list, mostrando los contactos.
24.	Case 2: donde e va a dar de alta a un contacto, donde se pide el nombre y teléfono del contacto, procede a manda llamar el método crear.
25.	Case 3: Requiere el número a eliminar mandando llamar el método eliminar.
26.	Case 4: manda llamar directamente el método almacén.
27.	Case 5: manda llamar la función salir, dando el agradecimiento por su visita.
28.	 En caso de elegir una opción que no se encuentre en el menú, se mostrara un mensaje el cual indicara “opción no valida, favor de intentarlo de nuevo”.
