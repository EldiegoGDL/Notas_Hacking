## Descripcion
* Can you get the flag?
Additional details will be available after launching your challenge instance.
* Is there more code than what the inspector initially shows?

## Solucion
revisamos la pagina y nos encontramos un botón que nos indicaba que el codigo estaba en los archivos asi que fui al codigo fuente y revise los archivos en el .css encontre un fragmento de la mitad de la bandera
```c
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */
```
 y en el archivo .js la otra mitad 
 ```
 function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_b8f4b022}
 ```
y asi encontamos la bandera

picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}
## Referencias