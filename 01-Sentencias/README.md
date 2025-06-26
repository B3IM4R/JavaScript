## Sentencias

Son instrucciones sintácticas y comandos que realizan acciones. Podemos tener tantas sentencias en nuestro código como queramos y se separan con un punto y coma.

**Ejemplo:** Separamos "Hola Mundo" en dos alertas.

~~~ JavaScript
alert("Hola"); alert("Mundo");
~~~

Para hacer el código más legible, las sentencias se escriben en líneas separadas:

~~~ JavaScript
alert("Hola");
alert("Mundo");
~~~

### Punto & Coma

Se puede omitir un punto y coma en la mayoría de los casos cuando existe un salto de línea y de igual forma funciona:

~~~ JavaScript
alert('Hola')
alert('Mundo')
~~~

Aquí, JavaScript interpreta el salto de línea como un punto y coma **implícito**. Esto se denomina **inserción automática de punto y coma**.

> [!NOTE] Nota
> En la mayoría de los casos, una nueva línea implica un punto y coma. Pero “en la mayoría de los casos” no significa **siempre**!


**Ejemplo:**

~~~ JavaScript
alert( 3 +
1
+ 2
);
~~~

El código da como resultado `6` porque JavaScript no inserta punto y coma aquí. Es intuitivamente obvio que si la línea termina con un signo más `+`, es una **expresión incompleta**, un punto y coma aquí sería incorrecto. Y en este caso eso funciona según lo previsto.

> [!WARNING] Tener Cuidado
> - En ocasiones JavaScript **falla** al asumir un punto y coma donde realmente se necesita.
> - Los errores que ocurren en tales casos son bastante difíciles de encontrar y corregir.

**Ejemplo:**

~~~ JavaScript
alert("Hola");

[1, 2].forEach(alert);
~~~

El resultado del código muestra "Hola", luego 1 y luego 2.

> [!CAUTION] Error que Podemos Obtener   
> ~~~ JavaScript
> alert("Hola")
>
> [1, 2].forEach(alert);
> ~~~

Ahora solo se ve el primer `Hola` y un error. Los números no aparecen más.
Esto ocurre porque JavaScript no asume un punto y coma antes de los corchetes `[...]`, entonces el código del primer ejemplo se trata como una sola sentencia.

Así es como lo ve el motor:

~~~ JavaScript
alert("Hola")[1, 2].forEach(alert);
~~~

Tal unión en este caso es simplemente incorrecta. Necesitamos poner un punto y coma después del `alert` para que el código funcione bien.

> [!TIP] Recomendación
> Colocar puntos y coma entre las sentencias, incluso si están separadas por saltos de línea. Esta regla está ampliamente adoptada por la comunidad.

### Comentarios

Los comentarios ayudan a describir lo que hace el código y por qué. Se pueden colocar en cualquier parte del script y no afectan en la ejecución del programa, porque este los ignora.

- **Comentario de una Línea:** Comienzan con dos caracteres de barra diagonal `//`. Lo que se escriba después en la misma línea es un comentario y puede ocupar una línea completa o seguir una sentencia.

    ~~~ JavaScript
    // Este comentario ocupa una línea propia.
    alert('Hello');

    alert('World'); // Este comentario sigue a la sentencia.
    ~~~

- **Comentarios de Varias Líneas:** Comienzan con una barra inclinada y un asterisco `/*` y terminan con un asterisco y una barra inclinada `*/`.


    ~~~ JavaScript
    /* Un ejemplo con dos mensajes.
    Este es un comentario multilínea.
    */
    alert('Hola');
    alert('Mundo');
    ~~~

> [!NOTE] Nota
> A veces puede ser útil deshabilitar temporalmente una parte del código:
> ~~~ JavaScript
> /* Comentando el código
> alert('Hola');
> */
> alert('Mundo');
> ~~~

Se debe tener en cuenta lo siguiente:

> [!CAUTION] ¡Los comentarios anidados no son admitidos!
> No puede haber `/*...*/` dentro de otro `/*...*/`. Eso terminaría en error.
> ~~~ JavaScript
> /*
> /* comentario anidado ?!? */
> */
> alert( 'Mundo' );
> ~~~