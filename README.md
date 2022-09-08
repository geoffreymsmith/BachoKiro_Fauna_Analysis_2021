[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

# Subsistence behavior during the Initial Upper Paleolithic in Europe: Site use, dietary practice and carnivore exploitation at Bacho Kiro Cave (Bulgaria).

This repository contains data and code used for analyses in:

> Smith, G.M. et. al. (2021) Subsistence behavior during the Initial Upper Paleolithic in Europe: Site use, dietary practice and carnivore exploitation at Bacho Kiro Cave (Bulgaria). https://doi.org/10.1016/j.jhevol.2021.103074

This readme file is based on the file and repository from [Sarah Pederzani's](https://www.eva.mpg.de/evolution/staff/sarah-pederzani?Fsize=-1%27A%3D0) work from [Bacho Kiro Cave](https://osf.io/tk9dc/) (Pederzani, 2021). I would like to thank her for continued assistance and advice with R, Rmarkdown and the construction of this repository. There is another version of this repository at: https://osf.io/62pbr/

### Requirements
To run the code, you will need to have an up-to-date version of [R](https://www.r-project.org/) and [RStudio](https://rstudio.com/) installed on your computer and a few CRAN packages (see below). 

All code and analyses were run using R version 4.0.2 (R Core Team 2020) on a Windows 10 operating system. 

```
# Install required packages
install.packages(c("readxl", "tidyverse", "gplots", "ggplots", "ggpubr", "kableExtra", "patchwork", "flextable","rstatix","captioner", "magick"))


The following versions of these R packages were used: 
readxl_1.3.1 (Wickham and Bryan 2019)
tidyverse_1.3.1 (Wickham et al. 2019)
ggplot_2_3.3.2  (Wickham 2016)
gplots_3.1.1 (Warnes et al 2020)
ggpubr_0.4.0 (Kassambara 2020)
kableExtra_1.3.4 (Zhu 2021)
patchwork_1.1.(Pedersen 2020)
flextable_0.6.6 (Gohel 2020)
rstatix_0.7.0 (Kassambara 2021)
captioner_2.2.3 (Alathea 2015)
magick_2.7.2 (Ooms 2021)

```
### Repository structure
`common/`: This contains basic documents necessary to generate the stylistic and bibliographic elements of the manuscript and supplementary information.

`data/`: This contains all the data files necessary to replicate the analysis and produce the figures and tables in the manuscript. 

`figures_export/`: Image files export from Rmd files as both .png and .tiff files. Within the repository only .png files are uploaded for due to space requirements.

`reports/`: Contains the Rmd files to generate the ms and SOM.

### Files contained in this repository

1) `common/`

   * `BK.bibliography.bib`- a bib file contains all the              references and bibliographic information.
   * `JHE.csl`- a csl file for journal citation style.
   * `reference.docx`- A reference word file with the base styles to reference in the Rmarkdown files for manuscript and supplementary.

2) `data/`

  * `abrasion.fig.csv` - bone abrasion data extracted from main database.
  * `arch.density.csv` - density of archaeological material (lithic and fauna) from excavation database.
  * `bear.wide.csv` - cave bear ageing data modified for plotting triangular graph.
  * `BK.MNE.MNI.csv` - Minimum Number of Elements (MNE) and Minimum Number of         Individuals (MNI) for all species from all layers (including contact zones). 
  * `bk.mpup.csv` - number of faunal remains recovered from each sector and all layers (including contact zones) at Bacho Kiro Cave.
  * `BK.plotted.fauna.csv` - number of specimens recovered from square, row and layer from Bacho Kiro Cave.
  * `bk.total.csv` - total number of faunal remains recovered from throughout the stratigraphic sequence at Bacho Kiro Cave.
  * `BK_excav_grid.csv` - dataframe to generate Bacho Kiro Cave site grid for Figure 2.1.
  
  * `bone.fusion.csv` - post-cranial fusion information from all layers at Bacho Kiro Cave.
  * `bone.fusion.taxa.csv` - post-cranial fusion information for identified species and bone elements and including range of fusion information (First Fusion Date [FFD] and Last Fusion Date [LFD] and Season of Fusion Date). 
  * `bone.remains.csv` - number of bone remains excavated from different sectors and layers I-K from Bacho Kiro Cave and the percentage of remains analysed. 
  * `BSC.hum.mod.csv` - human modifications (cut, scrape, marrow) across different carnivore and herbivore body size classes (BSC).
  * `BSM.csv` - number and percentage (%totalNSP) of carnivore and human modifications recorded in Layers I-K from Bacho Kiro Cave.
  * `buckets.1.csv` - total number of buckets and volume (litres and m^3^) excavated from Layers I-K.
  * `burn.csv` - number and percentage of burnt remains from Layers I-K.
  * `carn.mod.csv` - number and percentage of carnivore modifications in Layers I, J and K.
  * `fauna.per.litre.csv` - calculation of faunal density/litre by Layer and Square.
  * `fauna.studied.csv` - total number of bone specimens, number analysed and percentage from different sectors (Main, Niche 1) from Layers I-K.
  * `fauna_spatial.csv` - number of faunal specimens from excavation squares and layers at Bacho Kiro Cave.
  * `frag.size.summ.stats.csv` - summary statistics for bone fragment length from different layers.
  * `hmod.BSC.csv` - number and percentage of human modification types (cut, scrape, marrow) on main taxa from Bacho Kiro Cave.
  * `hum.mod.csv` - percentage of remains with cut, scrape and marrow marks from Layers I, J and K at Bacho Kiro Cave.
  * `ID.rate.csv` - number and percentage of faunal remains identifiable to species from different layers at Bacho Kiro Cave.
  * `IUP_site_comp.csv` - comparison of Initial Upper Palaeolithic sites with well preserved faunal remains.
  * `layer.frag.size.csv` - layer and bone fragment size for each piece plotted piece.
  * `layer.t.test.csv` - t-test comparing means of bone fragment size between Layers I,J and K; includes t-statistic, degrees of freedom and significance value.
  * `lithic.density.csv` - lithic density per litre for all layers and contact zones.
  * `main.taxa.frag.csv` - bone fragment length for main taxa (*Bos/Bison*, Cervidae and Ursidae) from Bacho Kiro Cave layers I-K.
  * `main.taxa.summ.stats.csv` - summary statistics for main taxa in Layers I, J and K.
  * `NISP.fig.csv` - Number of identified specimens (NISP) and percentage for all layers formatted for easier plotting.
  * `NISP.mod.csv` - NISP values regrouped into major species (*Bos/Bison*, Cervidae, Ursidae, carnivore, herbivore) by each layer, including contact zones.
  * `NISP.raw.csv` - raw NISP data.
  * `NSP.ident.csv` - Number of specimens studied.
  * `quant.standard.csv` - Quantification data for species from all layers; this includes NISP, minimum number of elements (MNE), minimum number of individuals (MNI), minimum anatomical units (MAU) and percentage minimum anatomical units (%MAU).
  * `read.fig.csv` - bone surface readability rearranged into low and high readability with percentage of total number of specimens.
  * `taxa.element.portion.csv` - quantification data by species and element portion (Cranium, Axial, Forelimb, Hindlimb, Foot); includes NISP, MNE, MNI.
  * `taxa.t.test.csv` - t-test data comparing mean bone length between main taxa (*Bos/Bison*, Cervidae and Ursidae) from Layer I; includes t-statistic, degrees of freedom and significance.
  * `total.studied.csv` - total number of bone remains analaysed and excavated.
  * `weath.fig.csv` - weathering data arranged into low and heavy weathering categories for easier visualisation.
  * `zones.density.csv` - taxa, element, scan zone, scan site abbreviation, number of specimens present and density recorded for various modern day taxa.
  * `carn_mod.tif` - photo figure of carnivore bone surface modifications.
  * `hum_mod.tif` - photo figure of human bone surface modifications.
  * `IUP_map.tif` - map of main IUP sites coded by bone preservation.
  * `PIMS.tif` - photo figure of projectile impact marks (PIMs)
  * `Site_grid.tif` - photo figure of site layout, site grid and stratigraphic sections.

  2.1 `SI/` 
  
  * `abrasion.SOM.csv` - detailed data on bone surface abrasion.
  * `bk.mpup.csv` - total number of piece plotted bone remains from sector and layer.
  * `BSC.mod.SOM.csv` - detailed data on human bone surface modifications type (cut, scrape, marrow) by body size class (BSC) and layer.
  * `BSM.carn.csv` - detailed data on carnivore bone surface modification types by layer.
  * `BSM.hum.csv` - detailed data on human bone surface modification types by layer.
  * `BSM.SOM.csv` - detailed data on human and carnivore bone surface modification by layer.
  * `burn.JHE.SOM.1.csv` - total number of burnt remains and percentage by layer.
  * `burn.JHE.SOM.2.csv` - detailed data on burn stages and number of specimens by layer. Based on Stiner et al., (1995).
  * `frag.summ.stats.SOM.csv` - summary statistics data for bone fragment length by layer.
  * `main.taxa.summ.stats.SOM.csv` - summary statistics data for bone fragment length by main taxa and layer.
  * `NISP.SOM.csv` - detailed breakdown of NISP data by layer.
  * `quant_mau.csv` - detailed table on quantification for each species, element and layer; includes NISP, MNE, MNI, MAU and %MAU.
  * `readability.SOM.csv` - detailed information on bone surface readability by layer.
  * `taxa_quant.csv` - detailed information for identifiable species including NISP, MNE, MNI.
  * `weathering.SOM.csv` - detailed information on bone weathering; based on Behrensmeyer (1978).
  * `zones.density.SOM.csv`

3) `figures_export/` 

  * `bear-age-1.png` - Figure 14
  * `bone-density-1.png` - Figure 6
  * `BSM-gen-1.png` - Figure 8
  * `BSM-taxa-1.png` - Figure 11
  * `BSM-taxa-portion-1.png` - Figure 12
  * `carn-mod-fig-1.png` - Figure 9
  * `frag-size-1.png` - Figure 4
  * `hum-mod-fig-1.png` - Figure 10
  * `IUP-map-1.png`- Figure 15
  * `NISP-1.png` - Figure 3
  * `PIMS-1.png` - Figure 13
  * `site-grid-1.png` - Figure 1
  * `spatial-1.png` - Figure 2
  * `taph-panel-1.png` - Figure 7
  * `taxa-element-1.png` - Figure 5
  
4) `reports/`

  * `BK_Main_2021.rmd` - RMarkdown document to generate `BK_Main_2021.docx`.
  * `BK_Main_2021.docx` - Word document generated from `BK_Main_2021.rmd`.
  * `BK_SOM_2021.rmd` - RMarkdown document to generate `BK_SOM_2021.docx`.
  * `BK_SOM_2021.docx` - Word document generated from `BK_SOM_2021.rmd`.


### References

Letaw Alathea (2015). captioner: Numbers Figures and Creates Simple Captions. R package version 2.2.3.
https://CRAN.R-project.org/package=captioner

Anna K Behrensmeyer (1978). Taphonomic and ecologic information from bone weathering. Paleobiology, 4(2), 150-162.

David Gohel (2021). flextable: Functions for Tabular Reporting. R package version 0.6.6.
https://CRAN.R-project.org/package=flextable

Alboukadel Kassambara (2021).rstatix: Pipe-Friendly Framework
for Basic Statistical Tests. R package version 0.7.0.
https://CRAN.R-project.org/package=rstatix

Alboukadel Kassambara (2020). ggpubr: 'ggplot2' Based Publication Ready Plots. R package version 0.4.0.
https://CRAN.R-project.org/package=ggpubr

Jeroen Ooms (2021). magick: Advanced Graphics and Image-Processing in R. R package version 2.7.2.
https://CRAN.R-project.org/package=magick

Thomas Lin Pedersen (2020).patchwork: The Composer of Plots.R package version 1.1.1.  https://CRAN.R-project.org/package=patchwork

Sarah Pederzani (2021). Data and Code for Subarctic climate for the earliest Homo sapiens in Europe. https://doi.org/10.17605/OSF.IO/TK9DC

R Core Team (2020). R: A language and environment for statistical computing. R Foundation for Statistical Computing, Vienna,Austria. URL
https://www.R-project.org/.

RStudio Team (2021). RStudio: Integrated Development Environment for R. RStudio, PBC, Boston, MA. http://www.rstudio.com/.

Mary Stiner et al (1995) Differential burning, recrystallization, and fragmentation of archaeological bone. Journal of archaeological science, 1;22(2):223-37.

Gregory R. Warnes, Ben Bolker, Lodewijk Bonebakker, Robert
Gentleman, Wolfgang Huber, Andy Liaw, Thomas Lumley, Martin
Maechler, Arni Magnusson, Steffen Moeller, Marc Schwartz and Bill Venables (2020). gplots: Various R Programming Tools for Plotting Data. R package version 3.1.1.
https://CRAN.R-project.org/package=gplots

Hadley Wickham and Jennifer Bryan (2019). readxl: Read Excel Files. R package version 1.3.1.
https://CRAN.R-project.org/package=readxl

Hadley Wickham et al., (2019). Welcome to the tidyverse. Journal of Open Source Software, 4(43), 1686,     https://doi.org/10.21105/joss.01686

Hadley Wickham (2016). ggplot2: Elegant Graphics for Data Analysis. Springer-Verlag New York. https://ggplot2.tidyverse.org

Hao Zhu (2021). kableExtra:Construct Complex Table with 'kable' and Pipe Syntax. R package version 1.3.4. https://CRAN.R-project.org/package=kableExtra

