---
title: QuickBio

hide: 
  - navigation
---

<style>
.md-content .md-typeset h1 { display: none; }
.md-sidebar.md-sidebar--secondary {
      display: none;
  }
/* Maximum space for text block */
.md-main__inner {
    justify-content: center;
}
.md-content {
  max-width: 75%; 
}
</style>
<!-- 
<p align="center">
  <a href="https://fastapi.tiangolo.com"><img src="https://fastapi.tiangolo.com/img/logo-margin/logo-teal.png" alt="FastAPI"></a>
</p> -->
<p align="center" style="margin-bottom: 0;">
  <em style="font-size: 3rem;">QuickBio</em>
</p>

<p align="center" style="margin-top: 0;">
  <em>Análisis de Biodiversidad</em>
</p>


---

<p align="center">
    <em>QuickBio automatiza el Análisis de Biodiversidad para los Estudios de Impacto ambiental, permitiendo al especialista enfocarse en la interpretación y análisis de resultados.</em>
</p>

---

En el desarrollo de los informes para los Estudios de impacto ambiental tenemos diversos procesos:

- **Validar** la información que recibimos.
- **Procesar** los datos.
- Realizar el **informe**.
- **Revisar** que todo esté correcto.

Por cada proceso y dependiendo del **Taxón** y el **número de especies** el desarrollo de estos pueden tardar días o semanas.

<p align="center">
  <picture align="center">
    <source media="(prefers-color-scheme: light)" srcset="assets/process_for_light.png">
    <source media="(prefers-color-scheme: dark)" srcset="assets/process_for_dark.png">
    <img alt="time module." src="assets/process_for_light.png">
  </picture>
</p>


QuickBio simplifica los procesos mediante [QuickBio Format](./guide/format/index.md), un sencillo Excel que es cargado a cada [módulo](./guide/index.md) de la aplicación obteniendo resultados al instante, transformando tediosas semanas de trabajo en eficiencia y precisión a un solo clic.

<p align="center" style="font-size: 1.5rem;">
  Modulos
</p>


[Guía de usuario](./guide/index.md)


<div class="grid cards" markdown>

-   __Validador de nombres__ 

    ---

    Valida los nombres de los registros de especies y obtén los nombres aceptados o sus sinónimos.

    [Guia](./guide/module/valid-names.md)

-   __Country Book__

    ---

    Autocompleta la información requerida de tu Taxón acorde al país.

    [Guia](./guide/module/country_book/index.md)

-  __Análisis de diversidad__

    ---
    Recorre tu data a travez del filtro y genera gráficas y tablas listas para tu informe.

    [Guia](./guide/module/analysis/index.md)


</div>


![ProInnovate](../assets/proinnovate.png)