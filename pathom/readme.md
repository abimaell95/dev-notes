# Pathom
## Introducción
Librería que provee un conjunto de funcionalidades para parsear peticiones [EQL](https://edn-query-language.org/eql/1.0.0/what-is-eql.html).

## ¿Cómo funciona?
### Resolvers
Los resolvers son piezas que funcionan como arcos para conectar a los nodos de nuestro grafo.
```
(pc/defresolver greetings [_ {:keys [name]}]
  {::pc/input  #{:name}
   ::pc/output [:greetings]}
  {:greetings (str "Hello" name)})
```
En este caso el resolver "greetings" nos va retornar como output un string "Hello {name}" dependiendo del nombre que enviemos como input.
``` 
{::pc/input  #{:name}
 ::pc/output [:greetings]}
```
La primera parte de un resolver contiene la información del contexto, en este caso la entrada y la salidad.
``` 
{:greetings (str "Hello" name)}
```
La segunda parte del resolver contiene la función que transforma mi contexto a lo que yo quisiera retornar.
