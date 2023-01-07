# Fichas de incidencia delictiva por regiones en el estado de Jalisco

Script para la elaboración de las fichas de incidencia delictiva en Jalisco en los delitos por razón de género.

- Realizado en R markdown

Fuentes:
- Datos del SESNSP
- Medidas y órdenes de protección del estado de Jalisco

Para la descripción regional de la elaboración se utilizó los diagnóstico regionales del IIEG


**Package requerida**


```{r include=FALSE}
install.packages(c("readxl", "dplyr", "ggplot2", "tidyverse", "esquisse", "tidyr", "plotly", "ggthemes", "janitor",
"kableExtra", "scales", "viridis", "RColorBrewer", "extrafontdb", "extrafont", "sysfonts", "lubridate", "knitr" "DT", "pagedown"))
```


**Para convertir un html a pdf**

Con la libreria pagedown deberas usar la función chrome_print y añadir la ruta o el path de donde se este guardando el html, por ejemplo

```{r include=FALSE}
chrome_print("C:/Users/Paola Viridiana/Documents/Fichas_incidencia_regiones_formato.html")
```

Por default se generará un pdf

**Para actualizar**

- No olvides cambiar las regiones y sus descripciones
- Añadir los logos institucionales
- Cada nueva actualización deberás cambiar el número de mes de cada uno de los periodos en *filter* por ejemplo en diciembre cambiar el -11- por -12-

```{r include=FALSE}
merge_regional %>% 
  mutate(Periodo = ymd(paste0(Año, "-", Mes, "-01"))) %>%
  filter(Periodo<="2022-11-01") %>%  
  group_by(Periodo)...
```
