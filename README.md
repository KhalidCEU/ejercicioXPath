## Ejercicio XPATH

> Usa Xpath para responder a las siguientes preguntas sobre el archivo [hamlet.xml](/hamlet.xml).

Nota: Consultas realizadas dentro de los sitios web [XPather](https://xpather.com/) y [FreeFormatter](https://www.freeformatter.com/xpath-tester.html)


#### 1. Los **títulos** de todas las **escenas del segundo acto**

**R:**
```
//ACT[2]/SCENE/TITLE
```


Devuelve:

```
1. A room in POLONIUS' house.
2. A room in the castle.
```

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

```
1. Long live the king!
2. In the same figure, like the king that's dead.
3. Looks it not like the king? mark it, Horatio.
```

....... _y otros mas_


#### 4. El segundo diálogo (speech) de Bernardo en el tercer acto

**R:**
```
//ACT[3]//SPEECH[SPEAKER='BERNARDO'][2]
```

No devuelve nada porque **no hay dialogo de este personaje** en **este acto**. Pero se puede comprobar usando **KING CLAUDIUS** en su lugar por ejemplo y verificar [hamlet.xml](hamlet.xml)


#### 5. Número de líneas de cada diálogo (speech)

**R:**

```
//SPEECH/ count(LINE)
```
o
```
for $s in //SPEECH return count($s/LINE)
```

#### 6. Número de líneas del diálogo (speech) con más líneas

**R:**

```
max(//SPEECH/ count(LINE))
```

Nos devuelve **60**

#### 7. **Todos** los diálogos (speech) de la tercera **PERSONA** del primer **PGROUP** dentro de **PERSONAE**

Si queremos obtener la 3ra PERSONA del 1er PGROUP dentro de PERSONAE
```
//PERSONAE//PGROUP[1]//PERSONA[3]        <!-- nos da ROSENCRANTZ  -->
```

**R:**

```
//SPEECH[SPEAKER = //PERSONAE//PGROUP[1]//PERSONA[3] ] <!-- nos da los SPEECH de ese SPEAKER  -->
```

Nos devuelve:

```
Element='<SPEECH>
   <SPEAKER>ROSENCRANTZ</SPEAKER>
   <LINE>Both your majesties</LINE>
   <LINE>Might, by the sovereign power you have of us,</LINE>
   <LINE>Put your dread pleasures more into command</LINE>
   <LINE>Than to entreaty.</LINE>
</SPEECH>'
Element='<SPEECH>
   <SPEAKER>ROSENCRANTZ</SPEAKER>
   <LINE>
      <STAGEDIR>To POLONIUS</STAGEDIR>  God save you, sir!</LINE>
</SPEECH>'
```
.... _y otros mas_
