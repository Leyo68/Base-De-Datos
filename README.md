# Base De Datos

**### Explicación Del Código Fuente**

En el proyecto se crearon dos paquetes:
Base de datos:
	Clases:

- BaseDeDatos
- ControlCliente
- ControlProducto
- ControlProveedor

JPanel:

- Principal
- Productos
- Proveedores
- Clientes
- GestionCliente
- GestionProducto
- GestionProveedor

Útil:
	Clases:

- Configuracion
- MySQL


**Clase Configuración**
En esta clase se declaran los variables que se utilizaran en la ejecución del programa, todas las variables se declaran en static, ya que no se tiene que instanciar con la clase para poder utilizarlos. Se declaran dos variables tipo string: id y titulo; también una variable acción que servirá como bandera para saber qué acción estamos ejecutando y finalmente una variable tipo MySQL llamada conexión, se declara nulo.
![imagen](https://user-images.githubusercontent.com/71055467/114496988-b8320000-9be6-11eb-87b8-cc43e2339d69.png)

**Clase MySQL**
En esta clase se encuentran las líneas de código que servirán para hacer la conexión con la base de datos, primero se importa las librerías necesarias que se utilizarán. También se declaran unas variables como final la variable llamada BD es el nombre de la base de dato, la variable USER es el usuario de nuestra base de datos como estamos trabajando con xampp el usuario es root, la variable PASS es donde contiene la contraseña, la variable SERVER contiene la dirección IP o el localhost, por último, se encuentra la variable tipo Connection llamada conexion.
![imagen](https://user-images.githubusercontent.com/71055467/114497001-c253fe80-9be6-11eb-90d6-34edcedbc349.png)

En esta clase tenemos un constructor que tiene una variable String llamada url en donde se encuentra el url y se le concatena la variable SERVER y BD, posteriormente se tiene un try catch, primero se carga el driver para poder conectarse con la base de datos. Posteriormente se crea una conexión con la base de datos en donde se pasa por parámetro las variables url, USER, PASS y se le asigna a la variable conexión; si todo este proceso se realiza con éxito, se manda un mensaje por consola diciendo: “Conectado”, de lo contrario se mandará un mensaje por pantalla: “Error al conectarse al servidor.
![imagen](https://user-images.githubusercontent.com/71055467/114497029-d0098400-9be6-11eb-8bd7-74ef8207e32d.png)

También se tiene un método llamado ejecutaSQL que recibe por parámetro una variable tipo String y devuelve un tipo de dato booleano, dentro de este método se encuentra un try catch en donde se tiene declarado la variable llamada consulta de tipo Statement que se le asigna la sentencia SQL que sirve para hacer la conexión con la base de datos. En la siguiente línea de código se cierra la conexión de la base de datos, y se realiza exitosamente se retorna true de lo contrario se manda un mensaje y se retorna un false.
![imagen](https://user-images.githubusercontent.com/71055467/114497041-d7309200-9be6-11eb-8914-bf7e3bc1f97a.png)

El método consultaSQL retorna un tipo de dato ResultSet y recibe por parámetro un String. Dentro del método se inicializa la variable rs tipo ResultSet, dentro del try catch se encuentra la variable llamada consulta de tipo Statement que se le asigna la sentencia SQL que sirve para hacer la conexión con la base de datos, con la variable rs se hace la consulta a la base de datos y se le pasa por parámetro el String sql. Si ocurre un error al comunicarse con la base de datos se mandará a un mensaje, al final se retornará la variable rs.
En esta clase también se tiene el método getter de la variable conexión.
![imagen](https://user-images.githubusercontent.com/71055467/114497052-e0b9fa00-9be6-11eb-9940-3344df338e3c.png)

**Clase BaseDeDatos**
Esta es la clase principal, en donde primero se importan las clases Configuracion y MySQL, en el método main se crea a instancia con la clase MySQL y se lama la clase llamada principal.
![imagen](https://user-images.githubusercontent.com/71055467/114497072-e9aacb80-9be6-11eb-8d33-39e5fc53b8d9.png)

**Clase Principal**
En esta clase hereda de la clase JFrame, se tiene un constructor, dentro del constructor se invoca el método unitComponents, también se le pone un título a la ventana, se hace visible y se bloquea la opción para que el usuario pueda redimensionar la ventana. Además, se declara los botones y el Label que se ocuparan en esta clase.
![imagen](https://user-images.githubusercontent.com/71055467/114497091-f3343380-9be6-11eb-8c47-518a8f5ce1e3.png)

En el método initcomponents se le da colores a los botones, se le da el tamaño de letra que tendrá los botones, también se le coloca en el botón una imagen que dependiendo que botón sea, asimismo se le pone el texto que contendrá cada botón. Por último, se deja indicado que el botón tendrá un evento que más adelante se programará. 
![imagen](https://user-images.githubusercontent.com/71055467/114497104-fa5b4180-9be6-11eb-9876-d31445d521bb.png)

Además, se tiene programado un JLabel se le da el tamaño de letra, se le inca que el texto que contendrá estará siempre centrado, por último, le colocamos el texto que contendrá este JLabel.
![imagen](https://user-images.githubusercontent.com/71055467/114497115-02b37c80-9be7-11eb-88d1-ce6093684c4f.png)

Por último, la clase Principal se programa los eventos que tendrán cada botones al ser presionado. 
![imagen](https://user-images.githubusercontent.com/71055467/114497119-07783080-9be7-11eb-903a-568f1fe133cf.png)

**Clase Productos**
La clase productos hereda de la clase JFrame, al principio se importa las librerías que se utilizaran. En el constructor se llama el método initcomponents, se vuelve visible la ventana, y se deshabilita la opción para que el usuario no pueda redimensionar la ventana, además, se llama el método mostrarTabla para que cada vez que se agregue un producto se modifique. Asimismo, se declararon los componentes que tendrá la ventana.
![imagen](https://user-images.githubusercontent.com/71055467/114497134-0f37d500-9be7-11eb-9f8e-3754b3edcb6d.png)

En el método initComponents se instancia los objetos con sus clases correspondientes, en este método se le da dimensiones y forma a todos los objetos de nuestra ventana, primero se le da el tamaño de letra que tendrá el JLable, con la otra línea de código se centra el texto, y se le coloca el texto que tendrá el JLabel. Después, en las siguientes líneas de código se le pone el texto que tendrá cada columna de nuestra tabla, y por último a la tabla se le agrega un ScrollPanel.3.
![imagen](https://user-images.githubusercontent.com/71055467/114497152-15c64c80-9be7-11eb-9281-a5d1dfcfb518.png)
![imagen](https://user-images.githubusercontent.com/71055467/114497172-237bd200-9be7-11eb-9bc2-6b92d8e605d2.png)

En el método initComponents también se programa los botones que tiene nuestra ventana. Con la línea de código setBackground se le da color al botón, con setFont se le pone el tipo y tamaño de letra al botón, con setIcon le ponemos una imagen al botón solo se pasa la dirección en donde se encuentra la imagen, con setText se le agrega el texto al botón, por último, con la línea de código addActionListener se indica que los botones se le programara un evento más adelante. Con los tres botones se hacen lo mismo para darles formato.
![imagen](https://user-images.githubusercontent.com/71055467/114497182-2aa2e000-9be7-11eb-8100-1b279da2f374.png)

Aquí se muestra el evento que tiene el botón agregar. Primero se cambia el texto que tendrá el título, se cambia el valor de la variable acción que se encuentra en la clase Configuración que dependiendo a la función que se está ejecutando cambiará de número, se hace visible la ventana de la clase GestionProducto y se invoca el método mostrarTabla para actualizar la información de la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497200-342c4800-9be7-11eb-9a37-28eff93a5e32.png)

Aquí se muestra el evento que tiene el botón Editar. Primero se invoca el método seleccionar_fila, después con una sentencia if comprobamos que la variable id contenga al menos 1 carácter, dentro de la condicional if se cambia el texto que tendrá el título, se cambia el valor de la variable acción que se encuentra en la clase Configuración que dependiendo a la función que se está ejecutando cambiará de número, se hace visible la ventana de la clase GestionProducto y se invoca el método mostrarTabla para actualizar la información de la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497212-3a222900-9be7-11eb-8a10-62d6da82e893.png)

Aquí se muestra el evento que tiene el botón Eliminar. Primero se invoca el método seleccionar_fila, después con una sentencia if comprobamos que la variable id contenga al menos 1 carácter, dentro de la condicional if se cambia el texto que tendrá el título, se cambia el valor de la variable acción que se encuentra en la clase Configuración que dependiendo a la función que se está ejecutando cambiará de número, se hace visible la ventana de la clase GestionProducto y se invoca el método mostrarTabla para actualizar la información de la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497224-43ab9100-9be7-11eb-8e43-97cacf1e4fc4.png)

Este método se declara una variable tipo int llamada fila que se le asigna el valor de -1, y a la variable id se le borra el contenido.
Posteriormente con un if se valida que se ha seleccionado solo una fila de la tabla si es así a la variable fila se le asigna el número de fila que se ha seleccionado, si se ha seleccionado más de una fila de la tabla se manda un mensaje en pantalla: “Seleccionar sólo un elemento”.
Con otro if si la variable fila es mayor a -1 se hace un casting para convertir el dato a tipo String y ese dato convertido se le asigna a la variable id de la clase configuración.
![imagen](https://user-images.githubusercontent.com/71055467/114497233-48704500-9be7-11eb-95c7-318963129c66.png)

En el método llamado mostrarTabla se encuentra el código que se hará para actualizar la tabla. Al inicio se inicia crea un arreglo tipo string el cual contendrá los títulos de la tabla, en la siguiente línea con la instancia DefaultTableModel se crea la tabla dinámica. También se muestra los datos que ya tiene en la base de datos. Dentro del try catch en la variable nf se guarda el número de filas que tiene nuestra tabla, con un while se recorre la tabla y se muestra los datos y al llegar al último se sale del ciclo repetitivo. Con la línea de código setDataVector se crea la tabla modelo con las filas y los títulos variable creados anteriormente. Con setModel se pasa por parámetro la tabla y con esto se actualiza la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497244-51f9ad00-9be7-11eb-99d2-8a0c4682fce9.png)

**Clase GestionProducto**
En esta clase se importan las librerías y clases a utilizar, primero se declaran todos los objetos a utilizar en la ventana, posteriormente se encuentra el constructor que recibe como parámetro un objeto tipo Frame y una variable boolean. Dentro del constructor se invoca el método initComponents y el método inicio, con la línea setLocationRelativeTo hacemos que la ventana aparezca en el centro de la pantalla y por último se hace visible la ventana.
![imagen](https://user-images.githubusercontent.com/71055467/114497264-5a51e800-9be7-11eb-89b6-c33a87ad83e5.png)
![imagen](https://user-images.githubusercontent.com/71055467/114497275-5e7e0580-9be7-11eb-84a0-31af9b3b8000.png)

En el método initComponents se encuentra programado los objetos que tiene la ventana, se programa los JLabel se le da tipo y tamaño de letra, con la línea de código setText se coloca el texto que tendrá el JLabel.
![imagen](https://user-images.githubusercontent.com/71055467/114497283-65a51380-9be7-11eb-8bdb-93a5f40111df.png)

En el método initComponents también se programa los botones, se le pone el texto que tendrá el botón y se le indica que posteriormente que el botón tendrá un evento.
![imagen](https://user-images.githubusercontent.com/71055467/114497300-6b9af480-9be7-11eb-98cf-ee1fc02ea097.png)

En el método inicio, primero se cambia el texto de label, después con un if se valida que la variable acción que se encuentra en la clase Configuración, si esa variable contiene el número dos se invoca el método rellenar el campo; si contiene el número 3 se invoca otros dos métodos. 
![imagen](https://user-images.githubusercontent.com/71055467/114497308-7190d580-9be7-11eb-8073-b9a0a987b462.png)

El método agregarProducto se invoca al momento de agregar un producto, primero se valida los campos, con un if si la variable valida no contiene nada se invoca el método agregar de la clase controlProducto y se pasa por parámetros el texto que contiene cada JTextField, si el método agregar retorna el valor true se manda un mensaje en pantalla: “Producto Agregado” y si devuelve el valor false se manda: “Error al agregar el producto”.
![imagen](https://user-images.githubusercontent.com/71055467/114497320-781f4d00-9be7-11eb-89b9-71b13111efd5.png)

El método editarProducto se invoca al momento de editar un producto, primero se valida los campos, con un if si la variable valida no contiene nada se invoca el método agregar de la clase controlProducto y se pasa por parámetros el texto que contiene cada JTextField, si el método agregar retorna el valor true se manda un mensaje en pantalla: “Producto Agregado” y si devuelve el valor false se manda: “Error al agregar el producto”.
![imagen](https://user-images.githubusercontent.com/71055467/114497344-82d9e200-9be7-11eb-8705-233702a707f5.png)

En el método eliminarProducto primero se invoca el método eliminar de la clase controlProducto y se asigna a la variable ejecuta. Después con un if-else si la variable ejecuta contiene el valor true se manda el mensaje: “Producto Eliminado” Correctamente y con la siguiente línea de código se cierra la ventana; si la variable ejecuta contiene un valor false se muestra: “Error al eliminar el producto”.
![imagen](https://user-images.githubusercontent.com/71055467/114497357-8a00f000-9be7-11eb-9093-61b479feaaf4.png)

En este método (validarCampos) se valida todos los campos de los JTextField, primeramente, se inicializa la variable msj, después se valida cada campo, si un campo no contiene el tipo de texto que se requiere se concatena texto a la variable msj, por último, se retorna el contenido de la variable msj.
![imagen](https://user-images.githubusercontent.com/71055467/114497364-8f5e3a80-9be7-11eb-8d6a-7dd2db97e0b7.png)

En el siguiente método (rellenarCampos), primero se crea una variable tipo ResultSet y se le asigna el valor que retorna el método producto de la clase ControlProducto, dentro de un try-Catch con el método next nos movemos a la siguiente fila, después ponemos el texto que contiene cada columna en el JTextField correspondiente; si ocurre un error se manda por pantalla un mensaje. 
![imagen](https://user-images.githubusercontent.com/71055467/114497373-97b67580-9be7-11eb-8523-1c7d9d09ec05.png)

En el siguiente método (desactivarCampos) se deshabilita todos los JTextfield para que no se pueda insertar más texto en ellos.
![imagen](https://user-images.githubusercontent.com/71055467/114497386-9edd8380-9be7-11eb-80fc-0b3bc9a149a2.png)

**Clase ControlProducto**
En esta clase primero se importan todas las clases y librerías que se ocuparan, en el método agregar y editar se reciben por parámetro 5 datos tipo String posteriormente se hace conexión con la base de datos, en el método agregar, se agregan las variables en la base de datos, y en el método editar se actualiza los campos. Por último, se retorna el método EjecutaSQL.
![imagen](https://user-images.githubusercontent.com/71055467/114497402-a8ff8200-9be7-11eb-8509-a79328a19345.png)
![imagen](https://user-images.githubusercontent.com/71055467/114497406-ae5ccc80-9be7-11eb-84d3-17f51267cce4.png)

En el método eliminar se eliminará un producto, este método retorna lo que contiene el método ejecutaSQL. En el método mostrar se declara la variable rs ResulSet, y se hace una consulta con lavase de datos con el método consultaSQL y se le asigna el valor a la variable rs y por último se retorna la variable rs.
![imagen](https://user-images.githubusercontent.com/71055467/114497417-b452ad80-9be7-11eb-9147-157f9376ae13.png)

El método mostrar nos servirá para mostrar lo que hay en la base de datos, primero se inicia la variable rs tipo ResulSet, se agrega en el String llamado sql la línea que se ocupa para conectarse con la base de dato. Por último, se hace la conexión con el método consultaSQL que se envía por parámetro la variable sql esto se le asigna a la variable rs. Por último, se retorna la variable rs.
![imagen](https://user-images.githubusercontent.com/71055467/114497426-ba488e80-9be7-11eb-97fe-d40cc84d396e.png)

El método getRows, primero se crea una variable tipo Resulset, se crea el String sql en la siguiente línea de código se hace la conexión con la base da datos. En el try-Catch se tiene un while que recorrerá toda la tabla y retornara lo que contiene en la fila cantidad. Si ocurre una excepción se manda un mensaje en pantalla. Por último, si el código del while no se ejecuta retorna un valor de 0.
![imagen](https://user-images.githubusercontent.com/71055467/114497435-c16f9c80-9be7-11eb-9587-d49fc654d2f8.png)

El método producto retorna un dato tipo ResultSet, primero se crea a variable rs y también el String llamado sql el cual selecciona todos los campos de la tabla producto cuando el código sea igual posteriormente se invoca el método consultaSQL y se pasa por parámetro la variable sql. Por último, se retorna el valor de rs. 
![imagen](https://user-images.githubusercontent.com/71055467/114497442-c6cce700-9be7-11eb-8b2f-87ff876d8215.png)

**Clase Proveedores**
En esta clase (Proveedores), primero se importa las librerías a utilizar en la dicha clase, también se declaran los componentes que tiene en la ventana. En el constructor se vuelve visible la ventana, y se deshabilita la opción para que el usuario no pueda redimensionar la ventana, además, se llama el método mostrarTabla para que cada vez que se agregue un producto se modifique.
![imagen](https://user-images.githubusercontent.com/71055467/114497456-d0eee580-9be7-11eb-966d-4d5deb6bcef3.png)
![imagen](https://user-images.githubusercontent.com/71055467/114497463-d51b0300-9be7-11eb-80d6-216b2141b64c.png)

En la clase initComponents se programa todos los objetos de nuestra ventana, se programa el tipo y tamaño de letra que tiene el Label y se pone el texto. También se programa la tabla en donde se mostrará los proveedores registrados, se pone el texto que tendrá las cabeceras de nuestra tabla. y por último a la tabla se le agrega un ScrollPanel.
![imagen](https://user-images.githubusercontent.com/71055467/114497478-dba97a80-9be7-11eb-8508-73e0f4cdf93c.png)

En esta parte del código se muestra la programación de los botones, se pone a cada botón el color de fondo, el tipo y tamaño de letra, una imagen y un texto que contendrá el botón, se le deja indicado que más adelante se programará un evento para estos botones.
![imagen](https://user-images.githubusercontent.com/71055467/114497487-e2d08880-9be7-11eb-935f-c08ef3aba15e.png)

En este método (seleccionar_fila) se declara una variable tipo int llamada fila que se le asigna el valor de -1, y a la variable id se le borra el contenido.
Posteriormente con un if se valida que se ha seleccionado solo una fila de la tabla si es así a la variable fila se le asigna el número de fila que se ha seleccionado, si se ha seleccionado más de una fila de la tabla se manda un mensaje en pantalla: “Seleccionar sólo un elemento”.
Con otro if si la variable fila es mayor a -1 se hace un casting para convertir el dato a tipo String y ese dato convertido se le asigna a la variable id de la clase configuración.
![imagen](https://user-images.githubusercontent.com/71055467/114497498-e95f0000-9be7-11eb-8d52-bce21ff63041.png)

En el siguiente método (mostrarTabla) al inicio se inicia crea un arreglo tipo string el cual contendrá los títulos de la tabla, en la siguiente línea con la instancia DefaultTableModel se crea la tabla dinámica. También se muestra los datos que ya tiene en la base de datos. Dentro del try catch en la variable nf se guarda el número de filas que tiene nuestra tabla, con un while se recorre la tabla y se muestra los datos y al llegar al último se sale del ciclo repetitivo. Con la línea de código setDataVector se crea la tabla modelo con las filas y los títulos variable creados anteriormente. Con setModel se pasa por parámetro la tabla y con esto se actualiza la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497521-f7148580-9be7-11eb-85c4-99a623d08df8.png)

Aquí se muestra el evento que tiene el botón agregar. Primero se cambia el texto que tendrá el título, se cambia el valor de la variable acción que se encuentra en la clase Configuración que dependiendo a la función que se está ejecutando cambiará de número, se hace visible la ventana de la clase GestionProveedor y se invoca el método mostrarTabla para actualizar la información de la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497532-fd0a6680-9be7-11eb-8012-fbd12037eeb1.png)

Aquí se muestra el evento que tiene el botón Editar. Primero se invoca el método seleccionar_fila, después con una sentencia if comprobamos que la variable id contenga al menos 1 carácter, dentro de la condicional if se cambia el texto que tendrá el título, se cambia el valor de la variable acción que se encuentra en la clase Configuración que dependiendo a la función que se está ejecutando cambiará de número, se hace visible la ventana de la clase GestionProveedor y se invoca el método mostrarTabla para actualizar la información de la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497544-04ca0b00-9be8-11eb-878d-b31f07d9ab4c.png)

Aquí se muestra el evento que tiene el botón Eliminar. Primero se invoca el método seleccionar_fila, después con una sentencia if comprobamos que la variable id contenga al menos 1 carácter, dentro de la condicional if se cambia el texto que tendrá el título, se cambia el valor de la variable acción que se encuentra en la clase Configuración que dependiendo a la función que se está ejecutando cambiará de número, se hace visible la ventana de la clase GestionProveedor y se invoca el método mostrarTabla para actualizar la información de la tabla.
![imagen](https://user-images.githubusercontent.com/71055467/114497549-098ebf00-9be8-11eb-83c6-b2aeb3a5fb79.png)

**Clase GestionProveedores**
En esta clase se importan las librerías y clases a utilizar, primero se declaran todos los objetos a utilizar en la ventana, posteriormente se encuentra el constructor que recibe como parámetro un objeto tipo Frame y una variable boolean. Dentro del constructor se invoca el método initComponents y el método inicio, con la línea setLocationRelativeTo hacemos que la ventana aparezca en el centro de la pantalla y por último se hace visible la ventana.
![imagen](https://user-images.githubusercontent.com/71055467/114497571-10b5cd00-9be8-11eb-9b7f-4d7ce0581a8f.png)
![imagen](https://user-images.githubusercontent.com/71055467/114497581-157a8100-9be8-11eb-8a42-9157c9610e7c.png)

En el método initComponents se encuentra programado los objetos que tiene la ventana, se programa los JLabel se le da tipo y tamaño de letra, con la línea de código setText se coloca el texto que tendrá el JLabel.
![imagen](https://user-images.githubusercontent.com/71055467/114497597-1ca18f00-9be8-11eb-9230-efd49f70cda4.png)

En el método initComponents también se programa los botones, se le pone el texto que tendrá el botón y se le indica que posteriormente que el botón tendrá un evento.
![imagen](https://user-images.githubusercontent.com/71055467/114497607-21fed980-9be8-11eb-9e37-91e651557519.png)

En el método inicio, primero se cambia el texto de label, después con un if se valida la variable acción que se encuentra en la clase Configuración, si esa variable contiene el número dos se invoca el método rellenar el campo; si contiene el número 3 se invoca otros dos métodos.
![imagen](https://user-images.githubusercontent.com/71055467/114497660-3e9b1180-9be8-11eb-9c8f-c215c9ae8f7d.png)

El método agregarProveedor se invoca al momento de agregar un proveedor, primero se valida los campos, con un if si la variable valida no contiene nada se invoca el método agregar de la clase controlProvedor y se pasa por parámetros el texto que contiene cada JTextField, si el método agregar retorna el valor true se manda un mensaje en pantalla: “Proveedor Agregado” y si devuelve el valor false se manda: “Error al agregar el proveedor”.
![imagen](https://user-images.githubusercontent.com/71055467/114497673-4490f280-9be8-11eb-8bbd-22ad22cf6ba9.png)

El método editarProveedor se invoca al momento de editar un proveedor, primero se valida los campos, con un if si la variable valida no contiene nada se invoca el método agregar de la clase controlProveedor y se pasa por parámetros el texto que contiene cada JTextField, si el método editar retorna el valor true se manda un mensaje en pantalla: “Proveedor Agregado” y si devuelve el valor false se manda: “Error al agregar el proveedor”.
![imagen](https://user-images.githubusercontent.com/71055467/114497681-4b1f6a00-9be8-11eb-9353-111feb9b1aeb.png)

En el método eliminarProveedor primero se invoca el método eliminar de la clase controlProveedor y se asigna a la variable ejecuta. Después con un if-else si la variable ejecuta contiene el valor true se manda el mensaje: “Proveedor Eliminado” Correctamente y con la siguiente línea de código se cierra la ventana; si la variable ejecuta contiene un valor false se muestra: “Error al eliminar el proveedor”.
![imagen](https://user-images.githubusercontent.com/71055467/114497692-507cb480-9be8-11eb-9575-383820b5cfd3.png)

En este método (validarCampos) se valida todos los campos de los JTextField, primeramente, se inicializa la variable msj, después se valida cada campo, si un campo no contiene el tipo de texto que se requiere se concatena texto a la variable msj, por último, se retorna el contenido de la variable msj.
![imagen](https://user-images.githubusercontent.com/71055467/114497704-55416880-9be8-11eb-8749-6a69645902bd.png)

En el siguiente método (rellenarCampos), primero se crea una variable tipo ResultSet y se le asigna el valor que retorna el método producto de la clase ControlProveedor, dentro de un try-Catch con el método next nos movemos a la siguiente fila, después ponemos el texto que contiene cada columna en el JTextField correspondiente; si ocurre un error se manda por pantalla un mensaje. 
![imagen](https://user-images.githubusercontent.com/71055467/114497713-5a061c80-9be8-11eb-9c4c-b40c70408219.png)

En el siguiente método (desactivarCampos) se deshabilita todos los JTextfield para que no se pueda insertar más texto en ellos.
![imagen](https://user-images.githubusercontent.com/71055467/114497728-60949400-9be8-11eb-9ab4-155ea5f8ad2c.png)

**Clase ControlProveedor**
En esta clase primero se importan todas las clases y librerías que se ocuparan, en el método agregar y editar se reciben por parámetro 5 datos tipo String posteriormente se hace conexión con la base de datos, en el método agregar, se agregan las variables en la base de datos, y en el método editar se actualiza los campos. Por último, se retorna el método EjecutaSQL.
![imagen](https://user-images.githubusercontent.com/71055467/114497760-71450a00-9be8-11eb-9c36-1fa922a82b47.png)

En el método eliminar se eliminará un proveedor, este método retorna lo que contiene el método ejecutaSQL. En el método mostrar se declara la variable rs ResulSet, y se hace una consulta con la base de datos con el método consultaSQL y se le asigna el valor a la variable rs y por último se retorna la variable rs.
![imagen](https://user-images.githubusercontent.com/71055467/114497771-773aeb00-9be8-11eb-8e20-7c99e257c684.png)

El método getRows, primero se crea una variable tipo Resulset, se crea el String sql en la siguiente línea de código se hace la conexión con la base de datos. En el try-Catch se tiene un while que recorrerá toda la tabla y retornara lo que contiene en la fila edad. Si ocurre una excepción se manda un mensaje en pantalla. Por último, si el código del while no se ejecuta retorna un valor de 0.
![imagen](https://user-images.githubusercontent.com/71055467/114497779-7c983580-9be8-11eb-81d5-1df61206e6ab.png)

El método proveedor retorna un dato tipo ResultSet, primero se crea a variable rs y también el String llamado sql el cual selecciona todos los campos de la tabla producto cuando el código sea igual posteriormente se invoca el método consultaSQL y se pasa por parámetro la variable sql. Por último, se retorna el valor de rs. 
![imagen](https://user-images.githubusercontent.com/71055467/114497789-81f58000-9be8-11eb-9cf0-035099cc7e7e.png)

**Clase Clientes**
En esta clase primero se importan las librerías y clases a utilizar, y se declaran los objetos de nuestra ventana, en el constructor se programa todo lo relaciono con la ventana.
![imagen](https://user-images.githubusercontent.com/71055467/114497818-8c177e80-9be8-11eb-94e7-01db9767051a.png)
![imagen](https://user-images.githubusercontent.com/71055467/114497829-8fab0580-9be8-11eb-9a01-5163d7d307d9.png)

En el método unitComponents se hace la programación de todos los objetos que contiene la ventana.
![imagen](https://user-images.githubusercontent.com/71055467/114497849-95a0e680-9be8-11eb-8e43-4272a83fa1f7.png)

Aquí se encuentra los eventos de cada botón.
![imagen](https://user-images.githubusercontent.com/71055467/114497858-9a659a80-9be8-11eb-84d8-f533fd67e274.png)

**Clase GestionCliente**
En esta clase se importan las librerías y clases a utilizar, primero se declaran todos los objetos a utilizar en la ventana. Dentro del constructor con la línea setLocationRelativeTo hacemos que la ventana aparezca en el centro de la pantalla y por último se hace visible la ventana.
![imagen](https://user-images.githubusercontent.com/71055467/114497878-a3ef0280-9be8-11eb-83d7-0db615e592f4.png)

En el método initComponents se encuentra programado los objetos que tiene la ventana, se programa los JLabel se le da tipo y tamaño de letra, con la línea de código setText se coloca el texto que tendrá el JLabel, también se programa los botones. 
![imagen](https://user-images.githubusercontent.com/71055467/114497890-a9e4e380-9be8-11eb-8e3e-474ecef84b77.png)

El método agregarCliente, primero se valida los campos, con un if si la variable valida no contiene nada se invoca el método agregar de la clase controlClientes y se pasa por parámetros el texto que contiene cada JTextField, si el método agregar retorna el valor true se manda un mensaje en pantalla: “Cliente Agregado” y si devuelve el valor false se manda: “Error al agregar Cliente”.
![imagen](https://user-images.githubusercontent.com/71055467/114497899-af422e00-9be8-11eb-9e1b-ded55af65c88.png)

El método editarClientes, primero se valida los campos, con un if si la variable valida no contiene nada se invoca el método agregar de la clase controlCliente y se pasa por parámetros el texto que contiene cada JTextField, si el método agregar retorna el valor true se manda un mensaje en pantalla: “Cliente Editado” y si devuelve el valor false se manda: “Error al editar el cliente”.
![imagen](https://user-images.githubusercontent.com/71055467/114497908-b5380f00-9be8-11eb-9e1b-092ee6f735d8.png)

El método eliminarCliente se invoca al momento de eliminar un cliente, y el método validarCampos verifica que en todos los campos se insertaron los tipos de datos según corresponda.
![imagen](https://user-images.githubusercontent.com/71055467/114497924-ba955980-9be8-11eb-8022-0771f67a517b.png)

**Clase ControlCliente**
En esta clase primero se importan todas las clases y librerías que se ocuparan, en el método agregar y editar se reciben por parámetro 5 datos tipo String posteriormente se hace conexión con la base de datos, en el método agregar, se agregan las variables en la base de datos, y en el método editar se actualiza los campos. Por último, se retorna el método EjecutaSQL.

![imagen](https://user-images.githubusercontent.com/71055467/114497949-c54fee80-9be8-11eb-8a11-3acfc78d303d.png)

El método eliminar, este método retorna lo que contiene el método ejecutaSQL. En el método mostrar se declara la variable rs ResulSet, y se hace una consulta con la base de datos con el método consultaSQL y se le asigna el valor a la variable rs y por último se retorna la variable rs.
![imagen](https://user-images.githubusercontent.com/71055467/114497967-cbde6600-9be8-11eb-808c-f382dd89e482.png)

El método producto retorna un dato tipo ResultSet, primero se crea a variable rs y también el String llamado sql el cual selecciona todos los campos de la tabla producto cuando el código sea igual posteriormente se invoca el método consultaSQL y se pasa por parámetro la variable sql. Por último, se retorna el valor de rs.
![imagen](https://user-images.githubusercontent.com/71055467/114497988-d4cf3780-9be8-11eb-8a43-38bfae18292b.png)

**### Explicación De La Base De Datos**


Debido a que en este tema se trabaja de la mano con la Base de Datos y la Programación, es por ello que todo lo anterior está sincronizado con una base de datos que se elaboró en la página de phpMyAdmin, en breve se describe lo que se hizo en ella.
Lo primero que se realizó fue crear una nueva base de datos, se le asignó el nombre de “tópicos”, y dentro de ella se crearon tres tablas que es donde contiene la información dependiendo de lo que es necesario, las tablas son; clientes, producto y proveedor.
En la siguiente captura se puede observar el nombre de las tablas y la interfaz gráfica de la página.
![imagen](https://user-images.githubusercontent.com/71055467/114498091-152eb580-9be9-11eb-865a-a51a6e1596c6.png)

A continuación, podemos ver la estructura de las tablas, con esto podemos ver que las propiedades coinciden con las que hemos puesto en el código fuente de cada una de ellas.
![imagen](https://user-images.githubusercontent.com/71055467/114498104-1a8c0000-9be9-11eb-9a36-3e749f22e8b0.png)

![imagen](https://user-images.githubusercontent.com/71055467/114498110-1d86f080-9be9-11eb-9ac7-354bd2eb2b5b.png)

![imagen](https://user-images.githubusercontent.com/71055467/114498116-2081e100-9be9-11eb-91da-e2f52260cfb2.png)

Cada uno de los campos que contiene cada tabla son los mismos que contienen en el diseño de la tabla que se hizo en el IDE Netbeans.
Los datos que contiene cada una de ellas se mostrará más adelante.


**### Resultados**


En este apartado consiste en ejecutar el programa elaborado y mostrar todo el proceso del resultado mediante capturas de pantalla.
 Al ejecutar el proyecto desde la clase BaseDeDatos lo primero que veremos es una interfaz en donde se muestra el título y tres botones que dirigen a cada una de ellas, y esta se trata de la clase Principal que es un JPanel.
![imagen](https://user-images.githubusercontent.com/71055467/114498177-414a3680-9be9-11eb-874c-49a2b0df8cb7.png)

Ahora si pulsamos el botón de Productos siendo un JPanel se ve de la siguiente manera;
![imagen](https://user-images.githubusercontent.com/71055467/114498191-46a78100-9be9-11eb-9ba2-e12997a66d99.png)

Podemos observar que dentro de la tabla ya se encuentran datos que se ingresó desde la base de datos de MYSQL, si queremos comprobar, nos vamos a la página y tomamos captura de ello y observamos lo siguiente;
![imagen](https://user-images.githubusercontent.com/71055467/114498205-4c04cb80-9be9-11eb-9b47-9d2e6c5c6cc3.png)

Podemos ver que dentro de la tabla producto, se encuentran los mismos datos que podemos ver en la ventana del programa hecho en NetBeans, esto se repite para todas las tablas, asimismo si queremos agregar, editar o eliminar, los cambios se reflejan en ambas tablas.
Si pulsamos en el botón que dice agregar nos muestra una nueva ventana en donde podemos agregar un nuevo producto.
![imagen](https://user-images.githubusercontent.com/71055467/114498230-53c47000-9be9-11eb-815c-146783ddde10.png)

Agregaremos un nuevo producto, pero si antes pulsamos el botón de aceptar aparece una ventana de dialogo en la cual nos avisa de que no hemos rellenado los campos y que valores acepta cada uno de ellos.
![imagen](https://user-images.githubusercontent.com/71055467/114498243-59ba5100-9be9-11eb-8c07-1eccbe3062d4.png)

Ahora sí vamos a insertar datos en cada uno de los campos.
![imagen](https://user-images.githubusercontent.com/71055467/114498249-5f179b80-9be9-11eb-97e2-ffb5b3b65cf6.png)

Y si hemos ingresado datos de manera correcta nos muestra una ventana con un mensaje como el siguiente;
![imagen](https://user-images.githubusercontent.com/71055467/114498263-65a61300-9be9-11eb-80ef-aba3c5d53b96.png)

Y nos regresa a la tabla de productos donde vamos a lograr visualizar el nuevo producto agregado.
![imagen](https://user-images.githubusercontent.com/71055467/114498270-69d23080-9be9-11eb-95b7-84520cc7e37b.png)

Pero como está conectado con la base de datos, ingresamos a la tabla de producto que se encuentra en el servidor local y vemos lo siguiente;
![imagen](https://user-images.githubusercontent.com/71055467/114498289-7060a800-9be9-11eb-9e61-33e43f598d38.png)

Vemos que al final de la tabla se encuentra el nuevo producto, con esto quiere decir que la base de datos está funcionando de manera correcta.
	Ahora si pulsamos el botón de Editar y no hemos seleccionado ninguna fila, nos mostrará un mensaje con un aviso de que es lo que debemos hacer
![imagen](https://user-images.githubusercontent.com/71055467/114498300-76ef1f80-9be9-11eb-9d0f-b3c81d955a33.png)

Es por eso que primero debemos seleccionar una fila para poder dar click en el botón, pasa lo mismo con el botón Eliminar, por ello seleccionamos la fila que queremos editar:
![imagen](https://user-images.githubusercontent.com/71055467/114498318-7ce50080-9be9-11eb-82c4-ec32603da502.png)

Una vez hecho lo anterior pulsamos el botón de Editar y todos los datos se mostrará en una ventana similar a la que aparece en agregar;
![imagen](https://user-images.githubusercontent.com/71055467/114498333-840c0e80-9be9-11eb-9cd8-604981708be2.png)

Como ya tenemos todos los campos rellenados lo que podemos hacer es cambiar alguno de ellos, o todos dependiendo de la necesidad del usuario, en nuestro caso en el nombre le pondremos “Galletas” y le damos en el botón de aceptar;
![imagen](https://user-images.githubusercontent.com/71055467/114498342-8a01ef80-9be9-11eb-9a39-84a94f35c5cf.png)

Una vez dado en el botón de aceptar nos muestra un mensaje en pantalla como el siguiente;
![imagen](https://user-images.githubusercontent.com/71055467/114498355-8ec6a380-9be9-11eb-8fbb-699028394b91.png)

Y en la tabla aparece el producto editado, con esto podemos decir que el segundo botón funciona correctamente, ahora vamos con el tercero que es el botón de Eliminar.
![imagen](https://user-images.githubusercontent.com/71055467/114498394-9f771980-9be9-11eb-8dc2-ee01d5b4dfdb.png)

Para el botón de eliminar primero tenemos que seleccionar una fila antes de pulsar el botón dicho de lo contrario nos muestra un mensaje siguiente;
![imagen](https://user-images.githubusercontent.com/71055467/114498410-a6059100-9be9-11eb-81c5-a51d53b00fcb.png)

Ahora seleccionaremos en nuestro caso la fila tres;
![imagen](https://user-images.githubusercontent.com/71055467/114498421-abfb7200-9be9-11eb-950f-63124903de54.png)

Pulsamos el botón Eliminar
![imagen](https://user-images.githubusercontent.com/71055467/114498432-b0c02600-9be9-11eb-955c-afac72c5bb1f.png)

La ventana anterior nos aparece para ver todos los datos que contiene la fila seleccionada y si no estamos seguros de eliminar, pulsamos el botón de cancelar y se cierra la ventana, pero si en verdad deseamos borrar, pulsamos el botón de aceptar y veremos el siguiente mensaje;
![imagen](https://user-images.githubusercontent.com/71055467/114498450-b87fca80-9be9-11eb-9b44-93cbbabc0110.png)

Y en la tabla veremos lo siguiente;
![imagen](https://user-images.githubusercontent.com/71055467/114498456-bcabe800-9be9-11eb-8b20-194596965193.png)

Nos damos cuenta de que ya no aparece el producto que seleccionamos anteriormente, con esto podemos decir que todos los botones funcionan de manera correcta.
Si queremos hacer cualquier modificación a alguna de las tablas simplemente las seleccionamos y pulsamos en el botón que deseamos.
	Por ejemplo, si seleccionamos el botón de proveedores nos muestra una tabla similar a la de productos en donde se encuentran todos los datos referentes a ello;
![imagen](https://user-images.githubusercontent.com/71055467/114498472-c3d2f600-9be9-11eb-9de5-90ca086d94b8.png)

Pasa lo mismo con cada uno de los botones que se encuentran dentro de esta ventana, la interfaz es la misma como la que se muestra en productos y las acciones también, la diferencia es que en este caso los datos que se modifican, agregan o modifican se harán en la tabla de proveedores evidentemente.
	De la misma forma ocurre con la tabla de clientes, si pulsamos su botón correspondiente, nos llevará a una interfaz similar a la anterior sólo que cambia el número de campos de cada uno porque es lo que hemos programado anteriormente.
![imagen](https://user-images.githubusercontent.com/71055467/114498488-cafa0400-9be9-11eb-8b24-7b54353ac810.png)


**Conclusión**

En conclusión, al programa realizado y explicado anteriormente en este documento, podemos decir que saber bien la interfaz es importante, ya que esta contempla el diseño que le dimos y también los componentes que utilizamos, para llevar a cabo este ejemplo.
Ya que los lenguajes no traen incorporada una base de datos y es por este el motivo por el cual realizamos una conexión al lenguaje de programación con sistema gestor de base de datos. De igual forma nos dimos cuenta que una base de datos es una conexión organizada de datos, y también existen diferentes formas de organizarlos de manera que nos facilite el acceso y manipulación de la información que esta agregada.
