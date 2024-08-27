---
title: Conceptos previos
hide: 
  - navigation
---

<style>

.md-sidebar.md-sidebar--secondary {
      display: none;
  }

.md-main__inner {
    justify-content: center;
}
.md-content {
  max-width: 75%; 
}
</style>

<p align="center">
    <em>La base de QuickBio es la simplicidad, evitar todo tipo de procesamiento manual por parte del especialista</em>
</p>

---

La simplificación de los procesos se resumen en `QuickBio Format`, un excel donde la dualidad `País/Taxón` registrada en la pestaña `project_info` dirigen las búsquedas y operaciones.

En la pestaña `records` tenemos `columnas sombreadas` que son **obligatorias** y `columnas no sombreadas` que dependerán del proyecto y se verán reflejadas en los **gráficos y tablas** de `Análisis de biodiversidad`, estas pueden estar presentes o no.

Dependiendo de `País/Taxón` existirán columnas que se autocompletarán al usar `Country book`.

El `Validador de nombres` sirve como filtro para todos los procesos mencionados, ya que al existir errores, evitará que la data se procese alertando al especialista.


## **Secuencia de procesos**

``` mermaid
sequenceDiagram
    autonumber
    
    participant Usuario
    participant AppNameValidator as Validador de nombres
    participant AppCountryBook as Country book
    participant AppBiodiversidad as Análisis de diversidad
    
    Note over AppNameValidator,AppBiodiversidad: Modulos

    Usuario->>AppNameValidator: QuickBio_format.xlsx
    AppNameValidator->>AppCountryBook: AcceptedNames.xlsx
    AppCountryBook->>AppBiodiversidad: CountryBook.xlsx
        
    Note right of AppBiodiversidad:  Descargar tabla y/o gráfico   
```

:   
    1. El usuario carga `QuickBio Format` especifico de cada `País/Taxón` para validar los nombres de las especies.
    2. El excel validado es subido a `Country book` para actualizar las columnas especificas del `País/Taxón`.
    3. Que será usado para obtener las tablas y gráficos en `Análisis de biodiversidad`

!!! note
    Para agregar más procesos dentro de cada módulo, bases de datos y recomendaciones pueden escribirme a:

    `italo.buitron@outlook.com`




