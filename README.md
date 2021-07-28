# Kotlin
## Basic Things

### Funciones
El comando fun lo utilizamos para declarar funciones.
1. **main** -> Función principal.
2. **private** ->

### Variables
1. **val** Variable no modificable. (si es String no se puede cambiar a Int)
2. **var** Variable modificable.  
En texto se declara *println{“Esta es mi $miVariable”}*

### Data Types
1. **String:** Cadenas de texto.  
2. **Int:** Numeros enteros (byte, short, int, long).  
3. **Float:** Numeros decimales (float, double).  
4. **Boolean:** Verdadero o Falso (bool).  
	- Pueden decidir que bloque de codigo se ejecuta.  
	- Se realizan operaciones logicas.

### Sentencia If
Evalua condiciones V o F y decide que bloque de codigo se ejecuta.  

1. **Operadores condicionales**
	- **>** Mayor que.
	- **<** Menor que.
	- **>=** Mayor o igual que.
	- **<=** Menor o igual que.
	- **==** Igualdad.
	- **!=** Desigualdad.
2. **Operadores logicos**
	- **&&** Operador '*y*' (Todas V para que se cumpla).
	- **||** Operador '*o*' (Una V para que se cumpla).
	- **!** Operador '*no*' (Negacion de los operadores logicos).  
### Sentencia Else
Ejecuta un bloque de codigo cuando no se cumple el If.  

### Sentencia Else If
Funciona como un nuevo If para poder concatenar varias sentencias.  
Se pueden escribir todos los que quieras ya que el If y el Else solo se pueden una vez.  

	val operadorLogico = 8
        if ((operadorLogico < 10 && operadorLogico > 2) || operadorLogico == 20){
            println("$operadorLogico es menor que 10 y mayor que 2, o igual a 20")
        }
        else if(operadorLogico == 50){
            println("El numero es $operadorLogico")
        }
        else if(operadorLogico != 40){
            println("$operadorLogico es distinto que 40")
        }
        else{
            println("$operadorLogico es mayor que 10 o menor que 2, y distinto a 20")
        }

### Sentencia When (Switch)  
Es una alternativa a la sentencia If y se utiliza cuando una condicion debe tomar muchos valores.  

	val pais = "USA"
        // when con String
        when(pais){
            "Argentina", "España", "Mexico" ->{
                println("El idioma es Español")
            }
            "USA", "England" ->{
                println("El idioma es Ingles")
            }
            else ->{
                println("No se conoce el idioma")
            }
        }
        // when con int (entre rangos)
        val edad = 19
        when(edad){
            in 0..17 -> {
                println("Es menor de edad")
            }
            in 18..110 -> {
                println("Es mayor de edad")
            }
            else ->{
                println("Esta como loquita")
            }

### Arrays / Arreglos
Es un tipo de estructura que sirve para trabajar con un conjunto de valores ordenados de un mismo tipo (String, Int, Float, etc).

    fun arrays(){
        val name = "Felipe"
        val lastname = "Coste"
        val age = "22"
	
	// Creacion del array
        val myArray = arrayListOf<String>()
	
	// Añadimos datos de uno en uno (array admite repetidos)
        myArray.add(name)
        myArray.add(lastname)
        myArray.add(age)
        println(myArray)
	
	// Añadir un conjunto de datos
        myArray.addAll(listOf("Masculino", "Soltero"))
        println(myArray)
	
	// Acceso a datos (arranca en 0)
        val myLastname = myArray[1]
        println(myLastname)
	
	// Modificar datos
        myArray[1] = "Fullaondo"
        println(myArray)
	
	// Eliminar datos
        myArray.removeAt(4)
        println(myArray)
    
    }

### Maps / Diccionarios
Es un tipo de estructura que sirver para agrupar datos no ordenados en una forma de Clave / Valor (Todas las claves tienen que ser de un mismo de dato y todos los valores de un mismo tipo de dato pero pueden ser distintos entre si). No pueden existir claves repetidas.

    private fun maps(){
        // Sintaxis
        var myMap: Map<String,Int> = mapOf()
        println(myMap)

        // Añadir elementos
        myMap = mutableMapOf("Felipe" to 1, "Facundo" to 2, "Kiven" to 5)
        println(myMap)

        // Añadir datos uno a uno
        myMap["Juan"] = 4
        myMap.put("Faca", 4)
        println(myMap)

        // Actualizar un dato (si agrego un dato con una clave repetida su valor cambia)
        myMap.put("Faca", 8)
        println(myMap)

        // Acceder a un dato
        println(myMap["Felipe"])

        //Borrar datos
        myMap.remove("Kiven")
        println(myMap)
    }

### Bucles For / While
Sirven para repetir una misma accion una determinada cantidad de veces.

    private fun bucles(){
        val myArray = listOf("Felipe", "Facundo", "Juan")
        val myMap = mutableMapOf("Carlos" to 1, "Pepe" to 2, "Saso" to 3)
        // For
        for (myString in myArray){ //Recorre la cant. de veces como datos tenga el array
            println(myString)
        }
        for (myElement in myMap){
            println("${myElement.key}-${myElement.value}")
        }
        for (x in 0..10){  //Desde el 0 hasta el 10 inclusive.
            println(x)
        }
        for (x in 0 until 10 step 2){  //Recorre 10 veces con saltos de a 2
            println(x)
        }
        for (x in 10 downTo 0){  //Cuenta regresiva
            println(x)
        }
        // While
        var z = 0
        while (z < 10){
            println(z)
            z++ // z += 2,3,4,etc.
        }
