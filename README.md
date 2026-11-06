**Consignas**

1. Investigación
   Responder en README.md las preguntas de todos los temas e indicar las fuentes consultadas.
   Tema 1: ¿Qué es TypeScript?
● **¿Qué es TypeScript y quién lo desarrolla?**
   TypeScript es un superconjunto de JavaScript desarrollado por Microsoft que agrega tipado estático opcional.

● **¿Qué diferencias tiene con JavaScript?**
   TypeScript es tipado estatico opciona mientras JavaScript es dinamico. El primero requiere un paso de transpilacion o compilación para convertirse en JavaScrip mientras navegadores y entornos nativos ejecutan a este ultimo.
   Fuente: https://www.typescriptlang.org/

● **¿Qué ventajas ofrece?**
   Su ventajas principales:
   • Detecta errores mientras se escribe el código, antes de ejecutarlo.
   • Mejorar el autocompletado y la refactorización en el editor.
   • Hace al código más mantenible y escalable.
   • Los tipos funcionan como documentación del propio codigo.

● **¿Cuál es su versión actual?**
   La versión actual de TypeScript es la 7.0.2

Tema 2: Crear y ejecutar un proyecto
● **¿Cómo se instala TypeScript en un proyecto?**
   Se instala con npm i -D typescript.
● **¿Para qué sirve el archivo tsconfig.json?**
   Es el archivo de configuración del proyecto. Le indica a TypeScript tres cosas:
      1. Qué archivos forman el proyecto: include. 
      2. Qué tan estricto debe ser al verificar tipos: strict y opciones relacionadas. 
      3. Cómo generar el JavaScript: versión (target), sistema de módulos (module) y carpeta de salida(outDir). 
   También define que la carpeta es un proyecto TypeScript. Sin tsconfig.json, tsc no sabe qué compilar y muestra la pantalla de ayuda. Lo leen tsc y el editor; Node y tsx no lo usan para verificar.

● **¿Qué hace el comando tsc?**
   tsc Verifica tipos y genera JavaScript

● **¿Qué diferencia hay entre ejecutar un archivo con tsc, tsx y node?**
   **tsc**: Verifica tipos y genera JavaScript Compilar
   **tsx**: Genera JavaScript sin verificar tipos
   **node archivo.ts**: Solo borra las anotaciones de tipo

Tema 3: Tipos básicos
● **¿Qué son los tipos string, number y boolean?**
   **string**: Valores en cadenas.
   **number**: Numeros sin hacer diferencia entre enteros y/o decimales.
   **boolean**: Solo 2 valores que son True(Verdadero) o False(Falso).

● **¿Cómo se declara un array con tipo?**
   El array se declara de la siguiente manera:
   let numeros: number[] = [1, 2, 3];
   let nombres: string[] = ["Ana", "Luis"];

● **¿Qué es un tipo unión?**
   Un tipo de unión permite que una variable pueda ser entre varios tipos.

● **¿Por qué se recomienda evitar any?**
   // any: desactiva la verificación (evitar)
   let cualquierCosa: any = "texto";
   cualquierCosa = 42;
   cualquierCosa.metodoQueNoExiste(); // Sin error al escribir; falla al ejecutar
   // unknown: acepta cualquier valor, pero obliga a verificar antes de usarlo
   let dato: unknown = "texto";
   dato.toUpperCase(); // Error
   if (typeof dato === "string") {
   dato.toUpperCase(); // Correcto: dentro del if es string
   }

**Tema 4: Funciones**
● **¿Cómo se indican los tipos de los parámetros?**
   Se escribe el nombre del parametro luego ":" y se indica su tipo.

● **¿Cómo se indica el tipo de retorno?**
   El tipo de retorno se indica de la siguiente manera:
   function sumar(a: number, b: number): number {
      return a + b;
   }

● **¿Qué es un parámetro opcional?**
   Es un tipo de paramentro que puede ser nulo.

● **¿Qué es un parámetro por defecto?**
   Valor preestablecido que se le asigna a un parametro en la firma de una fucion:
   function crear(nombre: string, rol: string = "USER"): void {
      console.log(`Usuario ${nombre} con rol ${rol}`);
      }

**Tema 5: Interfaces y type**
● **¿Qué es una interfaz y para qué sirve?**
   Uno de los principios básicos de TypeScript es que la verificación de tipos se centra en la forma que tienen los valores. Se usa en estructuras de objetos y clases, sobre todo cuando se necesita extends
   Fuente: https://www.typescriptlang.org/docs/handbook/interfaces.html

● **¿Qué es un type?**
   Un type es tipo de dato que es una variable.

● **¿Cómo se declara una propiedad opcional?**
   Una propiedad es opcional al ponerle un singo de interrogacion(?) al final del nombre.

● **¿Cuándo conviene usar cada uno?**
**Tema 6: Enums y tipos literales**
● **¿Qué es un enum?**
   Un enum permite a un desarrollador definir un conjunto de constantes con nombre. El uso de enum puede facilitar la documentación de la intención o la creación de un conjunto de casos distintos.

● **¿Qué es un tipo literal?**
   Un tipo literal es un subtipo más específico que restringe una variable, parámetro o propiedad a un valor exacto y concreto

● **¿En qué se parecen y en qué se diferencian?**   
   Permite limitar los valores que puede adquirir una variable. Sin embargo enum generan código JavaScript real en tiempo de ejecución mientras los tipos literal desaparecen completamente. El primero se define con palabras reservadas y el segundo combinando valores primitivos con operadores de unión.

● **¿En qué situaciones se puede usar cada uno?**
   Enum se usa cuando se desea menjar de constantes relacionadas. Mientrar los tipos literales cuando se necesiten uniones de cadenas o numeros.
   
   Fuentes: 
      https://www.typescriptlang.org/docs/handbook/literal-types.html 
      https://www.typescriptlang.org/docs/handbook/enums.html 