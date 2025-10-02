Taller de parcial
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
Que es esto? muy facil! Es un archivo el cual contiene las respuestas en formato de word a diferentes preguntas hechas para la practica de la parcial de programacion orientada a objeto, no viene con codigo esta vez debido a la naturaleza de las preguntas siendo gran parte de estas escritas y una que otra si en formato de codigo, por ende las preguntas que requieren de codigo vienen con sus respctivas imagenes que muestran el codigo relacionado

📋 Descripción
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
El repositorio contiene un word como se puede ver, aqui estan todas las preguntas que contenia el taller, cada pregunta trae su respectiva respuesta (A excpecion de la pregunta 17 y 19), las preguntas mas teoricas traen una explicacion medianamente detallada de su solucion y las que requieren codigo no traen mas explicacion que la visualizacion del codigo y su salida

🖋️ Contenido
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
El trabajo trae un total de 20 preguntas con respuestas (a excpecion de las preguntas 17 y 19 que solo contienen preguntas) si se quieren ver las preguntas y respuestas a continuacion se listaran todas, por parte de las preguntas no incluyendo el codigo de la pregunta

1. ¿Cuáles de los siguientes nombres existen como atributos accesibles directamente desde a?
Respuesta:
De las opciones dadas, todas menos la opción C son accesibles desde a, a.x no tiene ningún tipo de seguridad, a._y se cuenta como protegida, aunque esto no hace que sea imposible acceder a su información y x._A__z es la opción de name mangling con la cual se puede acceder sin problema a la información de __z que normalmente daría error por estar como privada
2. ¿Qué imprime?
Respuesta:
Imprime dos valores, un “false” y un “true”, ¿Por qué? Esto es debido a el “hasattr” lo que hace esta función es comprobar si un atributo existe dentro de un objeto, en esta situación se están comprobando dos cosas e imprimiendo el resultado en valor booleano dentro del objeto “a” que es un objeto perteneciente a la clase A, en el primer hasattr se esta comprobando la existencia del atributo __secret dentro de a, lo cual existe como tal pero no es el nombre con el cual Python ahora reconoce este atributo porque es privado por eso imprime el resultado booleano “False” porque como no reconoce al atributo con ese nombre, no existe para Python, por el otro lado _A__secret es la forma correcta de escribir el atributo __secret después del name mangling de Python por lo que ahora este si reconoce al atributo e imprime el valor booleano con “True”
3.  Verdadero/Falso (explica por qué)
    a) El prefijo _ impide el acceso desde fuera de la clase.
    b) El prefijo __ hace imposible acceder al atributo.
    c) El name mangling depende del nombre de la clase.
Respuesta:
a)	Falso, Es falso porque el prefijo _ aunque indique el atributo o modulo como protegido este no impide su acceso desde fuera de la clase
b)	Falso, Es falso porque el prefijo __ impide el uso directo de los atributos o módulos por fuera de las clases únicamente, dentro de las clases aun es usable normalmente
c)	Verdadero, el name mangling se escribe como “_Nombre de clase__atributo” por lo que cada name mangling cambia con respecto de la clase 

4. ¿Qué se imprime y por qué no hay error de acceso?
Respuesta:
Al final del código se va a imprimir el atributo self._token, primero que nada no se va a crear un error de acceso porque _token solamente marca al atributo como protegido pero no protegido por lo que no tiene name mangling y por ende aun es accesible desde cualquier parte, ahora por la parte de lo que se imprime, va en partes, primero se crea la clase Base en la cual se tiene un inicializador con el atributo _token después de esto se crea otra subclase llamada Sub la que hereda completamente la clase Base, esto hace que cuente con el inicializador y atributos de Base. Sub inicia un método llamado revelar el cual devuelve _token y al final por fuera de la clase se imprime “sub().reveal()” el Sub() crea un objeto que pertenezca a la clase Sub y hereda todas las características de Base y .reveal inicia el método de Sub, así imprimiendo el valor que retorna el cual es _token, por esto al final se imprime el mismo _token el cual es “abc”
5. ¿Cuál es la salida?
Respuesta:

<img width="116" height="41" alt="image" src="https://github.com/user-attachments/assets/75ff0c3c-e1d0-4028-b85f-6b3e2de50c6b" />

¿Por qué?
Se crea una super clase llamada Base, esta cuenta con un atributo protegido .__v, después de esto se crea una subclase la cual hereda a la superclase Base, Sub, después se usa el inicializador de la clase y con la función “supper()” traemos el inicializador de la superclase Base y con ello creamos él .__v de Base, continuamos ahora con el atributo .__v de Sub y para esto fue usada la función super() para poder tener los atributos .__v de ambas clases sin que se sobrescriban, se termina el código con un método de la subclase Sub el cual devuelve dos valores “self.__v” que es el .__v de Sub y “self._Base_v” que por ser el .__v de Base paso por name mangling y ahora se reconoce como ._Base__v Con todo el código listo finalizamos con la impresión del método de Sub creando un objeto de sub y aplicándole el método para obtener el valor (2, 1), la impresión no da error porque el .__v de Sub se maneja dentro de la clase y el .__ v de Base se trabaja con su respectivo name mangling al estar en otra clase

6. ¿Qué ocurre y por qué?
Respuesta:
El error recae en c.y, ¿por qué? Porque y no está definido a diferencia de x por esto cae el error en c.y y al ejecutar le programa se muestra

 <img width="921" height="73" alt="image" src="https://github.com/user-attachments/assets/51b9755d-f52b-4080-8d9c-2b4f2f03f6ad" />

Pero entonces ¿por qué c.x si está definido? Por el método __slots__ , el método slots hace que la clase a la que se la aplique Utilice únicamente los atributos que se le sean definidos “x” en este caso

7. Escribe el nombre correcto del atributo.
Respuesta:
Para que el atributo de la clase B sea protegido, se usa el prefijo _ un ejemplo seria
self._vista = 99 

8. ¿Qué imprime y por qué?
Respuesta:
Muestra “True”, “False”, “True”, esto lo hace porque primero, la función hasattr solo devuelve valores Booleanos al ser una función que comprueba algo, segundo, devuelve valores porque en Python los métodos también cuentan como atributos, simplemente que atributos de función, y tercero, devuelve True por _step porque al estar solo protegida conserva su nombre, False porque __tick ya no tiene su nombre original al ser privado, paso por un name mangling y Python ya no reconoce a __tick como un atributo existente, True porque _M__tick es el nuevo nombre con el que __tick existe al pasar por el name mangling

9. Escribe la línea solicitada.
Respuesta:
<img width="921" height="102" alt="image" src="https://github.com/user-attachments/assets/06514eba-01cf-409b-a687-a981b2b8b0b1" />

<img width="241" height="59" alt="image" src="https://github.com/user-attachments/assets/267d3b90-8c39-44b7-bb36-4d7f4746a50e" />

10. ¿Cuál de estos nombres es más probable que aparezca en la lista: __a, _D__a o a? Explica.
Respuesta:
Es mas probable que aparezca _D__a, en la línea de names lo que se hace es un ciclo for, en el cual por cada item en dir(d) (esta función la cual contiene todos los objetos del objeto d), que contengan la letra “a” en el objeto d se añadirán a una lista, en esta lista como “a” esta privada por su prefijo __ se le ha modificado el nombre por _D__a en lugar de __a por lo que a la lista se le añadirá _D__a porque 
1)	__a ya no existe como atributo que Python reconozca
2)	a en primer lugar no existía

11. Completa para que saldo nunca sea negativo.
Respuesta:
<img width="824" height="591" alt="image" src="https://github.com/user-attachments/assets/093c331e-0775-4b0e-973e-e6906530c6e5" />

<img width="824" height="591" alt="image" src="https://github.com/user-attachments/assets/56c802de-061e-4860-b4d7-92a00b3978d3" />

12. Convierte temperatura_f en un atributo de solo lectura que se calcula desde temperatura_c.
Respuesta:
<img width="510" height="355" alt="image" src="https://github.com/user-attachments/assets/fd3723b7-5d4b-46b6-b7e7-c71c3db41b38" />
<img width="129" height="59" alt="image" src="https://github.com/user-attachments/assets/f1a594c3-7f43-4cdf-ace6-6c2913fbb4f3" />

13. Haz que nombre sea siempre str. Si asignan algo que no sea str, lanza TypeError.
Respuesta:
<img width="625" height="510" alt="image" src="https://github.com/user-attachments/assets/d6d3a2b7-dc67-409c-a82f-641dbed8157b" />
<img width="229" height="48" alt="image" src="https://github.com/user-attachments/assets/288a901c-fd99-496a-ac7b-469e4eb2cae9" />
<img width="766" height="530" alt="image" src="https://github.com/user-attachments/assets/9da1f6fb-0caa-4495-8714-a2d96a0032f8" />

14. Expón una vista de solo lectura de una lista interna.
Respuesta:
<img width="470" height="468" alt="image" src="https://github.com/user-attachments/assets/0dcb86f8-d936-4d22-8ce9-d6da4af06e0c" />
<img width="363" height="51" alt="image" src="https://github.com/user-attachments/assets/351be530-460f-4e09-bb9f-2c73e4ca8365" />

15. Refactoriza para evitar acceso directo al atributo y validar que velocidad sea entre 0 y 200.
Respuesta:
<img width="921" height="536" alt="image" src="https://github.com/user-attachments/assets/765ba31f-8026-4b2a-83b0-d10c95690508" />
<img width="153" height="60" alt="image" src="https://github.com/user-attachments/assets/28ed0d5f-15dd-4f42-a58f-4b7441a64d45" />
<img width="846" height="146" alt="image" src="https://github.com/user-attachments/assets/13f03c75-e961-4bf1-b25e-8ddf875b57c6" />

16. Explica con tus palabras cuándo usarías _atributo frente a __atributo en una API pública de una librería.
Respuesta:
_atributo es un atributo protegido y __atributo es un atributo privado por lo que en una API publica usaría _atributo frente a __atributo en valores que funcionen dentro de clases, subclases pero que no necesita de name mangling, ósea atributos que no necesiten del máximo nivel de seguridad que tiene Python “los privados” 

17. ¿Qué problema hay aquí?
18. ¿Dónde fallará esto y cómo lo arreglas?
Respuesta:
El código falla en la línea “return self.__x”, pero ¿Por qué? Muy fácil, esto es porque por mas que se haya heredado la clase A el atributo se encuentra privado, ósea que cuenta con name mangling, el programa no está retornando nada porque self.__x ya no se llama así ahora se llama self._A__x haciendo referencia a la clase A con su atributo privado
19. Completa para exponer solo un método seguro de un objeto interno.
20. Escribe una clase ContadorSeguro con:
• atributo “protegido” _n
• método inc() que suma 1
• propiedad n de solo lectura
• método “privado” __log() que imprima "tick" cuando se incrementa
Muestra un uso básico con dos incrementos y la lectura final.
Respuesta:
<img width="633" height="784" alt="image" src="https://github.com/user-attachments/assets/ffa956b5-c67c-47bd-9534-e218b070a2f8" />
<img width="729" height="513" alt="image" src="https://github.com/user-attachments/assets/b1d62d8c-4a97-40ad-b18b-6a870706b559" />


Como se puede ver las preguntas no hacen mucho sentido por si solas, esto porque la mayoria se acompaña de un codigo, por eso es recomendable entrar al documento para entenderlas completamente

🛠️ Tecnologías Utilizadas
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
Microsoft word
Visual studio code

🔧 Uso del documento
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
Descarge el word y abralo, adentro encontrara todas las pregtunas y respuestas, si quiere tendra imagenes del codigo en las preguntas que requieran de este para recrearlo en visual studio o el lector de python que le agrade y asi probarlo de primera mano

<img width="611" height="484" alt="image" src="https://github.com/user-attachments/assets/4b2caa40-f2f6-4e58-ac6c-10b253627797" />

📄 Licencia
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
Este proyecto es de código abierto y está disponible para el uso publico

Autor: Diego Armando Pérez Solano
Fecha de creación: 27 de septiembre 2025
Nombre del proyecto: Taller parcial.docx



