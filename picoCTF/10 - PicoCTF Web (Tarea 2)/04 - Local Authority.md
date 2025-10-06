
## Descripcion:
* Can you get the flag?
Additional details will be available after launching your challenge instance.
* How is the password checked on this website?

## Solucion
nos encontamos con una pagina con solo un apartado de inicio de sesión revisamos el codigo fuente encontrando un .css vacio y un archivo.js con estos datos
```js
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

```

y en el codigo principal hay un script con un ciclo if para confirmar el inicio de secion asi que lo analisamos y vemos que el js es una funcion que esta guardando el usuario y contaseña.
```
if ( usernameFilterPassed && passwordFilterPassed ) {
      
        loggedIn = checkPassword(window.username, window.password);
        
        if(loggedIn)
        {
          document.getElementById('msg').innerHTML = "Log In Successful";
          document.getElementById('adminFormHash').value = "2196812e91c29df34f5e217cfd639881";
          document.getElementById('hiddenAdminForm').submit();
        }
        else
        {
          document.getElementById('msg').innerHTML = "Log In Failed";
        }
      }
      else {
        document.getElementById('msg').innerHTML = "Illegal character in username or password."
      }
```
asi que sabiendo esto los ponemos en la pagina y esto nos respondio 
![[Pasted image 20251005183441.png]]
y asi obtuvimos la bandera
## Referencias: