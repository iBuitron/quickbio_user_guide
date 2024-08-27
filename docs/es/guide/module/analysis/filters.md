Los filtros de QuickBio te permiten navegar a travez de tus datos.

Con el boton Filtros del panel izquierdo de opciones, puedes acceder a los filtros.

## **¿Cómo funcionan?**

<!-- [Recordemos como se ordenan las columnas]: ../../format/index.md#records -->

Primero, [Recordemos como se ordenan las columnas](../../format/index.md#records) y usaremos un ejemplo para entenderlo de la mejor manera




| Zonas     |                      |                      |                      | Taxonomía |               |              |                |                                      |
| :-------- | :------------------- | :------------------- | :------------------- | :-------- | :------------ | :----------- | :------------- | :----------------------------------- |
| Temporada | Unidad de vegetación | Estación de muestreo | Unidades de muestreo | Taxón     | División      | Orden        | Familia        | Especie                              |
| Humeda    | Bofedal              | ABC_a                | ABC_a-T1             | Flora     | Magnoliophyta | Apiales      | Apiaceae       | Chaerophyllum andicola               |
| Humeda    | Bofedal              | XYZ_b                | XYZ_b-T1             | Flora     | Magnoliophyta | Lamiales     | Orobanchaceae  | Castilleja pumila                    |
| Humeda    | Laguna               | XVM_j                | XVM_j-T1             | Flora     | Magnoliophyta | Lamiales     | Plantaginaceae | Callitriche terrestris subsp.turfosa |
| Humeda    | Laguna               | TUP_k                | TUP_k-T1             | Flora     | Magnoliophyta | Ranunculales | Ranunculaceae  | Ranunculus aquatilis                 |



El filtro contiene el resumen de cada una de las columnas pertenecientes a `Zonas` y `Taxonomía` relacionandolos.

Seleccionamos `Zonas`


### `Zonas`

    Etiqueta del filtro
    -   Unidad de vegetación
        -   Estación de muestreo
            -   Unidad de muestreo


    Datos asociados a cada Etiqueta del filtro
    -   Bofedal
        -   ABC_a
            -   ABC_a-T1
        -   XYZ_b
            -   XYZ_b-T1

    -   Laguna
        -   XVM_j
            -   XVM_j-T1
        -   TUP_k
            -   TUP_k-T1

Como se menciona en *'Recordemos...'*, los datos de una `columna anterior` engloban los datos de una `columna siguiente`, por lo cual, si en el filtro eliminamos la etiqueta `Bofedal` de `Unidad de vegetación`, se eliminaran todos los datos asociados a `Bofedal` quedando:

    -   Laguna
        -   XVM_j
            -   XVM_j-T1
        -   TUP_k
            -   TUP_k-T1

    Con lo cual nos aseguramos que solo se presetan los datos asociados a Laguna

Pero, si por otro lado, eliminamos la etiqueta `ABC_a` y `XVM_j` de `Estación de muestreo`, quedaría:


    -   Bofedal
        -   XYZ_b
            -   XYZ_b-T1

    -   Laguna
        -   TUP_k
            -   TUP_k-T1


    Con lo cual ahora, si nos intereza comparar dos Estaciones de muestreo de
    diferentes Unidades de vegetación, podremos hacerlo de una manera simple.


Hasta ahora, solo hemos eliminado etiquetas del grupo `Zonas`, que como vimos, eliminan los datos asociados tanto de `Zonas` como de `Taxonomías` (Recordemos que está marcada la opcion superior `Zonas`).

Ahora, usemos los datos de Taxonomia (Sigue marcado Zonas)

Con está nueva tabla (Se han agregado datos adicionales a ABC_a y TUP_k con los ordenes Lamiales)

| Zonas     |                      |                      |                      | Taxonomía |               |              |                |                                      |
| :-------- | :------------------- | :------------------- | :------------------- | :-------- | :------------ | :----------- | :------------- | :----------------------------------- |
| Temporada | Unidad de vegetación | Estación de muestreo | Unidades de muestreo | Taxón     | División      | Orden        | Familia        | Especie                              |
| Humeda    | Bofedal              | ABC_a                | ABC_a-T1             | Flora     | Magnoliophyta | Apiales      | Apiaceae       | Chaerophyllum andicola               |
| Humeda    | Bofedal              | ABC_a                | ABC_a-T1             | Flora     | Magnoliophyta | Lamiales     | Orobanchaceae  | Castilleja pumila                    |
| Humeda    | Bofedal              | XYZ_b                | XYZ_b-T1             | Flora     | Magnoliophyta | Lamiales     | Orobanchaceae  | Castilleja pumila                    |
| Humeda    | Laguna               | XVM_j                | XVM_j-T1             | Flora     | Magnoliophyta | Lamiales     | Plantaginaceae | Callitriche terrestris subsp.turfosa |
| Humeda    | Laguna               | TUP_k                | TUP_k-T1             | Flora     | Magnoliophyta | Ranunculales | Ranunculaceae  | Ranunculus aquatilis                 |
| Humeda    | Laguna               | TUP_k                | TUP_k-T1             | Flora     | Magnoliophyta | Lamiales     | Orobanchaceae  | Castilleja pumila                    |


Si ahora, eliminamos algúna etiqueta asociada a `Taxonomía` esta solo afectará a los datos asociados a `Taxonomía` y no afectará a `Zonas`.


Por ejemplo, vemos que todas las `Estaciones de muestreo` comparten el `orden` *Lamiales*

    -   Bofedal
        -   ABC_a
            -   ABC_a-T1
                +   Apiales
                +   Lamiales
        -   XYZ_b
            -   XYZ_b-T1
                +   Lamiales

    -   Laguna
        -   XVM_j
            -   XVM_j-T1
                +   Lamiales
        -   TUP_k
            -   TUP_k-T1
                +   Ranunculales
                +   Lamiales

Si eliminamos la Etiquetas *Apiales* y *Ranunculales* de `orden` en el filtro, quedaría:

    -   Bofedal
        -   ABC_a
            -   ABC_a-T1
                +   Lamiales
        -   XYZ_b
            -   XYZ_b-T1
                +   Lamiales

    -   Laguna
        -   XVM_j
            -   XVM_j-T1
                +   Lamiales
                
        -   TUP_k
            -   TUP_k-T1
                +   Lamiales

    Con ello, nos aseguramos de solo presentar los datos 
    del Orden Lamiales asociados a diferentes 
    Estaciones de muestreo comparadas en dos Unidades de vegetación.

    Suponiendo que estamos en Abundancia, estaríamos comparando 
    la cantidad de individuos del Orden Lamiales en diversisas 
    Estaciones de muestreo asociadas a sus respectavias Unidades de Vegetación

El cambio de Segmento de `Zona` a `Taxonomía` reinicia los filtros.

Cuando cambiamos, la lógica se invierte.

El filtro ahora marcado con `Taxonomía` eliminará todos los registros asociados al grupo `Taxonomía` (Como antes lo hacía `Zonas`), y si mientrás está seleccionado el segmento `Taxonomía` eliminamos alguna etiqueta de `Zonas`, esta solo modificará al grupo `Zonas`.