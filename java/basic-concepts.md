## Lambda vs Api Stream

### Lambda
Es una forma de escribir una funcion anonima.<br>
Ejemplo<br>
button.addActionListener(e -> System.out.println("Click"));<br>

La lambda simplemente representa una función. Se le puede asignar una interfaz funcional.<br>
Ejemplo<br>
Predicate<Integer> esPar = numero -> numero % 2 == 0; <br>
System.out.println(esPar.test(8));

En los dos ejemplos no existe un stream.

### Api Stream
La Stream API sirve para transformar, filtrar, ordenar y reducir colecciones.<br>
Ejemplo<br>
List<String> resultado = nombres.stream()
        .filter(nombre -> nombre.length() > 4)
        .toList();

Aquí sí aparece una lambda:<br>
nombre -> nombre.length() > 4 <br>
La lambda solo sirve como filtrar.
El Stream es el que realiza todo el procesamiento.

### Relacion
Una lambda puede existir sin el Api Stream y un Stream utiliza lambdas para definir que hacer con los datos.