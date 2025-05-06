## Ejercicio XPATH

> Usa Xpath para responder a las siguientes preguntas sobre el archivo [hamlet.xml](/hamlet.xml).

Nota: Consultas realizadas dentro del sitio web [XPather](https://xpather.com/)


#### 1. Los **títulos** de todas las **escenas del segundo acto**

**R:**
```
//ACT[2]/SCENE/TITLE
```


Devuelve:
1. A room in POLONIUS' house.
2. A room in the castle.

#### 2. ¿Cuántas veces habla Hamlet?

**R:**
```
count(//SPEECH[SPEAKER='HAMLET'])
```


Devuelve : **359**

#### 3. El texto de las líneas que contengan la palabra "king"

**R:**
```
//LINE[contains(text(), 'king')]
```


Devuelve :

1. Long live the king!
2. In the same figure, like the king that's dead.
3. Looks it not like the king? mark it, Horatio.

....... _y otros mas_


#### 4. El segundo diálogo (speech) de Bernardo en el tercer acto

**R:**
```
//ACT[3]//SPEECH[SPEAKER='BERNARDO'][2]
```

No devuelve nada porque **no hay dialogo de este personaje** en **este acto**. Pero se puede comprobar usando **KING CLAUDIUS** en su lugar por ejemplo y verificar [hamlet.xml](hamlet.xml)

