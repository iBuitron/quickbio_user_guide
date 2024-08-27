---
title: QuickBio Format
---

<style>

.mermaid {
    display: flex;
    justify-content: center;
    
    
}
</style>



QuickBio format consta de dos pestañas:

- `project_info`
- `records`

!!! warning
    El nombre de las pestañas no puede ser modificado, pero puedes agregar más pestañas que no afectarán al procesamiento de datos.

!!! warning

    Existen `columnas sombreadas` que son **obligatorias** y que no pueden modificarse ni eliminarse.

    Las `columnas no sombreadas` son **opcionales** de acuerdo a las necesidades del proyecto. 

    El nombre usado para cada columna se verá reflejado en los gráficos y tablas.

    !!! tip
        Prueba **renombrar** el nombre de una columna o **agregar**/**eliminar** más columnas, ¡estos se verán reflejados en los gráficos y tablas! 

        Dale un vistazo a **QuickBio_format_flora.xlsx** como ejemplo de la estructura del excel.

## Pestañas

### **`project_info`**
:   Esta pestaña contiene la información del proyecto.

   
| project_id                                                                         | project_name        | project_type                         | year | specialist             | country | taxon |
| :--------------------------------------------------------------------------------- | :------------------ | :----------------------------------- | :--- | :--------------------- | :------ | :---- |
| Id del proyecto generado por QuickBio usado para el registro historico de especies | Nombre del proyecto | Tipo de proyecto (EIA, MEIA, ITS...) | Año  | Nombre del responsable | País    | Taxón |

:   **Columnas obligatorias:** `country`, `taxon`

!!! note

    Las columnas `project_id`, `project_name`, `project_type`, `year`, `specialist` pueden estar vacías en esta versión, el modelo de registros históricos de especies para el proyecto está en proceso de implementación y posteriormente será requerido.


### **`records`**

:   
La pestaña `records` se divide en `5 grupos`:

    - `dates`
    - `zones`
    - `taxonomy`
    - `data`
    - `coordinates`

    estas presentan columnas especificas


!!! warning
    Las tablas y gráficos mantienen el orden de las columnas de `zones` y `taxonomy`, este orden es importante para el procesamiento de los datos y se explica en los ejemplo de cada grupo.
        

#### **dates**
:   **Columna obligatoria:**

    + `Fecha` en formato `DD/MM/YYYY`.
      
#### **zones**

:   Contiene las columnas de zonificación del proyecto.

    **Columna obligatoria:** 

    + `Temporada` sin el año, el año se especifica en la pestaña `project_info`.

??? example

    - Orden de las columnas del grupo `zones`: 
    
        Temporada / Ecosistemas / Estaciones de muestreo / Unidades de monitoreo

        + Dentro de la `Temporada` hay `Ecosistemas`, cada `Ecosistema` tiene sus `Estaciones de muestro` y dentro de cada `Estación de muestro` existen sus respectivas `Unidades de monitoreo`.

    ``` mermaid
    stateDiagram-v2
        state Temporada {
            [*] --> Ecosistemas
            
            state Ecosistemas {
                [*] --> Estación_de_muestreo

                state Estación_de_muestreo {
                    [*] --> Unidad_de_monitoreo
                }
            }
        }
    ```

    Este ordenamiento es especifico de cada proyecto, pueden existir más o menos columnas con diferentes nombres.


#### **taxonomy**

:   Contiene las columnas con la clasificación taxonomica del grupo taxonómico.

    **Columna obligatoria:** 

    + `Especie`

??? example

    - Orden de las columnas del grupo `taxonomy`: 
    
        Phylum / Clase / Orden / Familia / Especie

        + Dentro del `Phylum` hay diversas `Clases`, cada `Clase` posee sus propios `Ordenes`, cada `Orden` contiene sus respectivas `Familias` que terminan en las `Especies`.

    ``` mermaid
    stateDiagram-v2

        state Phylum {
            [*] --> Clase
            
            state Clase {
                [*] --> Orden

                state Orden {
                    [*] --> Familia

                    state Familia {
                        [*] --> Especie

            
                    }
                }
            }
        }       
    ```

    Este ordenamiento es especifico de cada proyecto, pueden existir más o menos columnas con diferentes nombres.
   

#### **data**

:   Contiene las columnas que serán procesadas para la obtención de gráficos y tablas. 

    **Columna obligatoria:** 
    
    + `abundance`

!!! warning

    El grupo `data` contiene columnas especificas del `País/Taxón` que **no pueden ser modificadas o eliminadas** que se autocompletarán al usar `Country book`


#### **coordinates**

:   Contiene los puntos de coordenadas de los registros de cada especie

    **Columnas obligatorias:** 
    
    + `latitude`
    + `longitude`
