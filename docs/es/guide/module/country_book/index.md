# **Country book**

<p align="center">
    <em>Los requerimientos de cada país dependen de sus legilasciones ambientales y sus entidades evaluadoras.</em>
</p>

---

`Country book` automatiza la obtención de datos para las columnas especificas de cada `País/Taxón` en el grupo `data` de `QuickBio Format`  

## **Datos extraídos** 

Las columnas del grupo `data` empiezan con alguno de estos `TAG` seguido de la fuente:

- `category`: Estado de la especie (EN-VU-NT-LC ...)
- `notes`: Notas de la fuente
- `common_name`: Nombre común
- `distribution_country`: Países en los cuales se encuentra distribuida la especie.
- `distribution_local`: Localidades dentro del país en los cuales se encuentra distribuida la especie.
- `ecoregion`: Ecorregiones dentro del país en los cuales se encuentra distribuida la especie.
- `spanish_name`: Nombre en español.
- `english_name`: Nombre en ingles.

!!! example

    - category_`iucn`: Estado acorde a IUCN.
    - category_`cites`: Estado acorde a CITES.
    - distribution_country_`iucn`: Países en los cuales se encuentra distribuido acorde a IUCN.
    - ecoregion_`leon`: Ecoregiones acorde a B. Leon.
    - spanish_name_`plenge`: Nombre en español acorde a M. A. Plenge.

!!! info

    La presencia/ausencia de estos `TAG` dependen si existen en las fuentes usadas.