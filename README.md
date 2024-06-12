# 5-primera-aplicacion

1. [Crear primera aplicación en Scala](#schema1)


<hr>

<a name="schema1"></a>

## 1. Crear primera aplicación en Scala
### **Paso 1:Configurar un Proyecto Scala*
1. Crea un nuevo directorio para tu proyecto.
2. Abre Visual Studio Code y navega hasta el directorio de tu proyecto.
3. Abre una nueva terminal en Visual Studio Code: ve a `"Terminal" > "Nueva Terminal"`.
4. En la terminal, ejecuta el siguiente comando para crear un nuevo proyecto Scala usando sbt (Scala Build Tool):
```bash
sbt new scala/scala-seed.g8
```
5. Sigue las instrucciones en la terminal para proporcionar un nombre para tu proyecto.
6. Espera a que sbt descargue las dependencias y cree la estructura del proyecto.
### **Paso 2: Explorar el Proyecto Creado**
Después de crear el proyecto, verás una estructura de directorios similar a esta:

```css

mi-proyecto/
  ├── build.sbt
  ├── project/
  │   └── build.properties
  └── src/
      └── main/
          └── scala/
              └── miapp/
                  └── Hello.scala
```
- `project/`: Este directorio contiene los archivos de configuración de SBT.
- `src/main/scala/miapp`: Aquí es donde colocarás tu código fuente Scala. Verás un archivo `Main.scala` como punto de entrada para tu aplicación.
- `target/`: Este directorio contendrá los archivos compilados y otros artefactos generados por SBT.
### **Paso 3: Escribir y Ejecutar tu Código**
1. Abre el archivo Main.scala ubicado en `src/main/scala/miapp`.
2. Escriba tu código Scala dentro de este archivo. Puedes modificar el contenido existente o escribir tu propio código.
3. Guarda el archivo (Ctrl+S).
4. Para compilar y ejecutar tu aplicación, abre una terminal en Visual Studio Code y ejecuta el siguiente comando:
```bash
sbt run
```
Esto compilará y ejecutará tu aplicación Scala. Verás la salida de tu aplicación en la terminal.

[Hello.scala](./primer_app/src/main/scala/miapp/Hello.scala)
```scala
package miapp

object Hello extends Greeting with App {
  println(greeting)
}

trait Greeting {
  lazy val greeting: String = "hello"
}
```
Esto significa que el objeto `Hello` pertenece al paquete miapp. Para utilizar este objeto desde otro archivo Scala, deberías importar el paquete `miapp`:
```scala
import miapp.Hello

object Main extends App {
  Hello.main(Array())
}
```

1. **Paquete `miapp`:**

- `package miapp`: Organiza el código en el paquete `miapp`.
2. **Objeto `Hello`**:

- `object Hello extends Greeting with App`: Declara un objeto `Hello` que extiende el trait Greeting y también implementa el trait `App`.
- `println(greeting)`: Imprime el valor de `greeting`, que se obtiene del trait `Greeting`.
3. **Trait `Greeting`**:

- `trait Greeting`: Define un trait llamado `Greeting`.
- `lazy val greeting: String = "hello"`: Define una propiedad `greeting` que es un valor perezoso (`lazy val`) que se inicializa con la cadena `"hello"` cuando se accede por primera vez.

### **Ejecución del Código**
Cuando ejecutas este programa, `Hello` extiende `App`, por lo que el código dentro del cuerpo del objeto `Hello` se ejecutará automáticamente. En este caso, `println(greeting)` se ejecutará, lo que imprimirá `hello` en la consola.
