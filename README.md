# METALoci: identifying 3D genome hubs

![alt METALoci](https://github.com/3DGenomes/Sox9_METALoci/blob/main/pictures/METALoci_logo.png)

METALoci relies on spatial autocorrelation analysis, classically employed in geostatistics, to describe how the variation of a variable depends on space at a global and local scales (e.g., identifying contamination hotspots within a city). METALoci repurposes this type of analysis to quantify spatial genome hubs of similar epigenetic properties. Briefly, the overall flowchart of METALoci consists of four steps. First, a genome-wide Hi-C normalized matrix is taken as input and the top interactions selected. Second, the selected interactions are used to build a graph layout (equivalent to a physical map) using the Kamada-Kawai algorithm with nodes representing bins in the Hi-C matrix and the 2D distance between the nodes being inversely proportional to their normalized Hi-C interaction frequency. Third, epigenetic/genomic signals, measured as coverage per genomic bin (e.g., ChIP-seq signal for H3K27ac), are next mapped into the nodes of the graph layout. The fourth and final step involves the use of a measure of autocorrelation (specifically, the Local Moran’s I or LMI) to identify nodes and their neighborhoods with an enrichment of similar epigenetic/genomic signals.

This Python [Jupyter notebook](https://github.com/3DGenomes/Sox9_METALoci/blob/main/jupyter/Sox9_E13.5_METAloci.ipynb) can be used as example on how to analyze the Sox9 locus from the mouse genome on its differential enhancer hubs during development in gonadal cells (that is, at E13.5 days during development).

Contributors
************

METALoci is currently developed at the [MarciusLab](http://www.marciuslab.org>) with the contributions of Juan A. Rodríguez as well as the conceptual inputs from Oscar Lao.

Data for Sox9 example, as part of our [BioRxiv manuscript](DOI), generated at the [Lupiañez Lab](https://lupilab.wordpress.com) of MDC Berlin by Irene Mota-Gomez.

Dependencies
************
METALoci relies on a series of standard libraries such as SciPy, NumPy (1.21.6), Pandas (1.3.5), Matplotlib (3.5.2), seaborn (0.11.2) as well as other specialized libraries such as GeoPandas (0.10.2), NetworkX (2.6.3), libpysal (4.6.2), ESDA (2.4.1), and pyBigWig library from deepTools (0.3.18).
