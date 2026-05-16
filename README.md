# 📊 GraphMaster — VizLab
### Scientific Graphics for Research Publications as a Bioinformatic

> Aprendiendo a crear gráficos de alta calidad para artículos de investigación.  
> Desde cero, con herramientas open source, paso a paso.

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--5643--5909-brightgreen)](https://orcid.org/0009-0000-5643-5909)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rubén%20López-blue)](https://www.linkedin.com/in/ruben-lopez-hernandez-39a0231a8/)
[![Máster](https://img.shields.io/badge/Máster-Bioinformática%20VIU%202026--2027-orange)](https://www.universidadviu.com/int/maestria-bioinformatica?_gl=1*3pbk3n*_up*MQ..*_gs*MQ..&gclid=CjwKCAjwq6DQBhBVEiwA4ZD5XMFdeuqBfMcYMPrnxz5DRKze8nyw1S9u48A_xzDNCJ2MJRUTxE3gQBoCoFQQAvD_BwE&gclsrc=aw.ds&gbraid=0AAAAADp9oYA5NMUO5FfdkXewgVC5SRJN7)

---

## 👤 Sobre este repositorio

Este repositorio documenta mi proceso de aprendizaje en la creación de gráficos bioinformáticos de alta calidad para artículos en Journals, siguiendo el programa **VizLab** — un sistema de aprendizaje progresivo por misiones.

El objetivo es desarrollar habilidades en visualización estadística y publicación académica utilizando exclusivamente herramientas **open source**, aplicables directamente a mis investigaciones en bioinformática.

| | |
|---|---|
| **Estado actual** | En progreso activo |
| **Nivel VizLab** | Mundo 1 → Fundamentos ✅ |
| **Entornos de trabajo** | RStudio (R) + Google Colab (Python) |
| **Publicación objetivo** | Journals indexados (JCR / Scopus) |

---

## 🛠 Entorno de trabajo

### Python (Google Colab / Jupyter)

| Herramienta | Versión | Uso |
|---|---|---|
| Python | 3.x (Anaconda) | Lenguaje principal |
| Matplotlib | 3.10.6 | Motor de gráficos base |
| Seaborn | 0.13.2 | Gráficos estadísticos elegantes |
| Pandas | 2.3.3 | Manejo de datos tabulares |
| NumPy | 2.3.5 | Cálculo numérico |
| SciPy | 1.16.3 | Pruebas estadísticas |
| Jupyter Notebook | — | Entorno de trabajo interactivo |

### R (RStudio)

| Herramienta | Uso |
|---|---|
| R 4.6+ | Lenguaje estadístico |
| ggplot2 | Gráficos publicables (Tidyverse) |
| DESeq2 | Expresión génica diferencial |
| EnhancedVolcano | Volcano plots |
| pheatmap | Heatmaps con clustering |
| ComplexHeatmap | Heatmaps para journals de alto impacto |
| factoextra | PCA y análisis multivariante |

### Instalación rápida

```bash
# Python — con pip
pip install matplotlib seaborn pandas numpy scipy

# Python — con Anaconda (recomendado, ya incluye todo)
# https://anaconda.com/download
```

```r
# R — instalar Tidyverse
install.packages("stringi", type = "binary")
install.packages("tidyverse")

# R — instalar paquetes de Bioconductor
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install(c("DESeq2", "EnhancedVolcano", "pheatmap"))
```

### Verificar que todo funciona

```python
# verificar_entorno.py
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
import numpy as np
print("✓ Todo listo para hacer ciencia!")
```

```r
# En RStudio
library(tidyverse)
sessionInfo()  # Muestra versiones de todos los paquetes
```

---

## 🗂 Estructura del repositorio

```
GraphMaster/
│
├── mundo_1_fundamentos/
│   ├── m1_anatomia_grafico/
│   │   └── notas.md
│   ├── m2_instalacion_rstudio/
│   │   ├── verificar_entorno.R
│   │   └── notas.md
│   └── m3_instalacion_colab/
│       ├── verificar_entorno.ipynb
│       └── notas.md
│
├── mundo_2_volcano_plot/
│   ├── m4_teoria_volcano/
│   │   └── notas.md
│   ├── m5_volcano_rstudio/
│   │   ├── volcano_DESeq2_airway.R      ← código comentado
│   │   └── volcano_airway.tiff          ← figura exportada 300 DPI
│   └── m6_volcano_colab/
│       ├── volcano_colab.ipynb
│       └── volcano_colab.tiff
│
├── mundo_3_heatmap/
│   ├── m7_teoria_heatmap/
│   ├── m8_heatmap_rstudio/
│   │   ├── heatmap_pheatmap.R
│   │   └── heatmap.tiff
│   └── m9_heatmap_colab/
│       ├── heatmap_seaborn.ipynb
│       └── heatmap_colab.tiff
│
├── mundo_4_estadistica_visual/
│   ├── violin_boxplot_ggplot2.R
│   └── violin_boxplot.tiff
│
├── mundo_5_omicas_avanzadas/          🔒 (próximamente)
│   ├── pca_biplot/
│   └── manhattan_plot/
│
├── figures/                           ← figuras finales exportadas (TIFF / PDF)
├── data/                              ← datasets de ejemplo usados en los scripts
├── master_config.py                   ← configuración global rcParams (Python)
├── master_config.R                    ← configuración global ggplot2 theme (R)
└── README.md
```

---

## 📐 Configuración global para publicación

### Python — `master_config.py`

```python
# master_config.py — aplicar al inicio de cada script
import matplotlib as mpl

mpl.rcParams.update({
    'font.family'      : 'Arial',
    'font.size'        : 10,
    'axes.titlesize'   : 11,
    'axes.labelsize'   : 10,
    'xtick.labelsize'  : 9,
    'ytick.labelsize'  : 9,
    'legend.fontsize'  : 9,
    'axes.linewidth'   : 0.8,
    'lines.linewidth'  : 1.5,
    'figure.dpi'       : 150,    # pantalla
    'savefig.dpi'      : 300,    # guardado — mínimo para journals
    'savefig.format'   : 'tiff',
    'savefig.bbox'     : 'tight',
    'savefig.transparent': False,
})

# Tamaños estándar (en pulgadas)
UNA_COLUMNA  = (3.35, 2.50)   # 8.5 cm  — journals de 1 columna
DOS_COLUMNAS = (7.00, 4.50)   # 17.8 cm — journals de 2 columnas
PANORAMICO   = (7.00, 3.00)   # figura ancha y baja
```

### R — `master_config.R`

```r
# master_config.R — cargar al inicio de cada script de ggplot2
library(ggplot2)

theme_publicacion <- theme_classic(base_size = 10, base_family = "Arial") +
  theme(
    plot.title    = element_text(size = 11, face = "bold"),
    axis.title    = element_text(size = 10),
    axis.text     = element_text(size = 9),
    legend.text   = element_text(size = 9),
    strip.text    = element_text(size = 10, face = "bold")
  )

# Tamaños estándar para exportar
exportar_tiff <- function(nombre, ancho = 7, alto = 5) {
  tiff(nombre, width = ancho, height = alto, units = "in", res = 300)
}
```

---

## 📚 Contenido por mundo (VizLab)

### Mundo 1 — Fundamentos ✅

| Misión | Tema | Entorno | Estado |
|---|---|---|---|
| M1 | ¿Qué es un gráfico científico? | Teoría | ✅ |
| M2 | Instalar RStudio + Tidyverse | R | ✅ |
| M3 | Configurar Google Colab | Python | ✅ |

### Mundo 2 — Volcano Plot 🔄

| Misión | Tema | Entorno | Estado |
|---|---|---|---|
| M4 | Teoría del Volcano Plot | Teoría | ✅ |
| M5 | Volcano Plot con DESeq2 | R | ✅ |
| M6 | Volcano Plot con matplotlib | Python | ✅ |

### Mundo 3 — Heatmap de expresión ⌚

| Misión | Tema | Entorno | Estado |
|---|---|---|---|
| M7 | Teoría del Heatmap | Teoría | 🔄 |
| M8 | Heatmap con pheatmap | R | 🔒 |
| M9 | Heatmap con seaborn | Python | 🔒 |

### Mundo 4 — Estadística Visual 🔒

| Misión | Tema | Entorno | Estado |
|---|---|---|---|
| M10 | Violin + Boxplot | R / Python | 🔒 |
| M11 | Barras de error e IC 95% | R / Python | 🔒 |

### Mundo 5 — Ómicas Avanzadas 🔒

| Misión | Tema | Entorno | Estado |
|---|---|---|---|
| M12 | PCA biplot | R / Python | 🔒 |
| M13 | UMAP | Python | 🔒 |
| M14 | Manhattan Plot (GWAS) | R | 🔒 |

---

## 🎯 Conceptos clave aprendidos

### Tipos de gráficos y cuándo usarlos

| Gráfico | Uso ideal | Herramienta |
|---|---|---|
| Volcano Plot | Expresión génica diferencial (RNA-seq) | EnhancedVolcano / matplotlib |
| Heatmap | Patrones de co-expresión multi-muestra | pheatmap / seaborn |
| Violin + Boxplot | Comparar distribuciones entre grupos | ggplot2 + ggpubr |
| PCA Biplot | Control de calidad y agrupamiento de muestras | factoextra / sklearn |
| Barras + error | Comparar medias entre grupos independientes | ggplot2 / matplotlib |
| Scatter + regresión | Correlación entre dos variables continuas | ggplot2 / seaborn |
| Manhattan Plot | Asociación genómica (GWAS) | qqman / matplotlib |
| Kaplan-Meier | Análisis de supervivencia | survminer / lifelines |

### Barras de error — diferencias importantes

| Métrica | Fórmula | Cuándo usar |
|---|---|---|
| SD | √(Σ(x−x̄)²/n−1) | Describir variabilidad de la muestra |
| SEM | SD / √n | Precisión del estimador de la media |
| IC 95% | x̄ ± 1.96 × SEM | Inferencia — preferido por Nature, Cell, NEJM |

> ⚠️ Siempre especificar en la leyenda qué representan las barras de error.

---

## ✅ Checklist pre-publicación

Antes de enviar cualquier figura a un journal:

- [ ] Todos los ejes tienen etiqueta con unidades
- [ ] El título comienza con "Figura N. ..."
- [ ] La leyenda especifica qué representan las barras de error
- [ ] Paleta de colores apta para daltónicos (colorblind-safe)
- [ ] La figura funciona en escala de grises
- [ ] Guardada en TIFF o PDF a ≥ 300 DPI
- [ ] Tamaño apropiado para el layout (1 columna: 3.35" / 2 columnas: 7.0")
- [ ] Tipografía ≥ 8 pt en todo el gráfico
- [ ] El n por grupo está especificado en leyenda o título
- [ ] p-value ajustado (padj / FDR) en lugar de p-value crudo

---

## 🔬 Pipeline completo de trabajo

```
datos_brutos.csv
      │
      ▼
1. Cargar con pandas / readr
      │  pd.read_csv('datos.csv') | read_csv("datos.csv")
      ▼
2. Explorar y limpiar
      │  df.describe(), df.isnull().sum() | summary(df)
      ▼
3. Análisis estadístico
      │  scipy.stats (t-test, ANOVA) | DESeq2, t.test()
      ▼
4. Crear figura
      │  matplotlib + seaborn | ggplot2 + extensiones
      ▼
5. Checklist pre-publicación
      ▼
6. Exportar
      plt.savefig('Fig1_volcano.tiff', dpi=300)
      ggsave('Fig1_violin.tiff', dpi=300, width=7, height=5, units="in")
```

---

## 📖 Recursos de referencia

- [Matplotlib documentation](https://matplotlib.org/stable/gallery/)
- [Seaborn documentation](https://seaborn.pydata.org/examples/)
- [ggplot2 documentation](https://ggplot2.tidyverse.org/)
- [EnhancedVolcano (Bioconductor)](https://bioconductor.org/packages/EnhancedVolcano/)
- [ColorBrewer — paletas científicas](https://colorbrewer2.org/)
- [Nature — guía de figuras para autores](https://www.nature.com/nature/for-authors/formatting-guide)
- [Lifelines — análisis de supervivencia en Python](https://lifelines.readthedocs.io/)

---

## 📈 Progreso personal

```
Mundo 1 — Fundamentos          ████████████████████  100% ✅
Mundo 2 — Volcano Plot         ████████████████████  100% ✅
Mundo 3 — Heatmap              ████░░░░░░░░░░░░░░░░   20% 🔄
Mundo 4 — Estadística Visual   ░░░░░░░░░░░░░░░░░░░░    0% 🔒
Mundo 5 — Ómicas Avanzadas     ░░░░░░░░░░░░░░░░░░░░    0% 🔒

XP total acumulado: 150 / 500
```

---

## 📝 Notas personales

Este repositorio es parte de mi plan de fortalecimiento como investigador con miras a la publicación de artículos en journals indexados. Los scripts aquí documentados son completamente reproducibles y están comentados línea por línea para facilitar la comprensión y reutilización.

Actualmente cursando el **Máster Universitario en Bioinformática** en la Universidad Internacional de Valencia (VIU), generación 2026–2027.

Publicación indexada previa: *Revisión sobre Linfoma de Burkitt*, Revista de Medicina e Investigación UAEMéx, Vol. 14, No. 1, 2026.

---

*Última actualización: Mayo 2026*

[![CC BY-NC 4.0](https://licensebuttons.net/l/by-nc/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc/4.0/)

# Scientific-visualization-lab--VizLab--graphics-for-bioinformatics
Collection of publication-quality scientific figures generated during my Master's in Bioinformatics (VIU, 2026–2027). Includes volcano plots, heatmaps, PCA plots and more, built with R (ggplot2, DESeq2) and Python (matplotlib, seaborn). — Rubén López Hernández | ORCID: 0009-0000-5643-5909
