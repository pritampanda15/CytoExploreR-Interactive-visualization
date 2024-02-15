# CytoExploreR-Interactive-visualization
CytoExploreR: A Comprehensive Open-Source R Package for Interactive Cytometry Data Analysis

Sure! Below is the entire code placed into a GitHub Readme.md file format:

```markdown
# Interactive Analysis of Cytometry Data in R

## Overview
This repository provides code for interactive analysis of cytometry data in R, authored by Pritam Kumar Panda from the German Cancer Research Center (DKFZ) in Germany.

## Setup
Before running the code, ensure you have set your working directory to the appropriate location. You can do this with the following command:
```R
setwd("/Users/pritam/facs_data_analysis_R/FACS/CytoExploreR")
```

## Packages Installation
Install the required packages:
```R
install.packages("tidyverse")
install.packages("knitr")
install.packages("ggplot2")
install.packages("remotes")
install.packages("BiocManager")
install.packages("devtools")
install.packages("kableExtra")
install.packages("devtools")

# Bioconductor packages
BiocManager::install(c("flowCore", "flowWorkspace", "openCyto", "flowAI", "ggcyto", "CytoML"))
```

## CytoExploreR Installation
Install CytoExploreR and CytoExploreRData from GitHub:
```R
devtools::install_github("DillonHammill/CytoExploreR")
devtools::install_github("DillonHammill/CytoExploreRData")
```

## Required Packages
Load the necessary packages for analysis:
```R
library(flowCore)
library(CytoML)
library(flowAI)
library(flowWorkspace)
library(ggcyto)
library(tidyverse)
library(openCyto)
library(knitr)
library(kableExtra)
library(dplyr)
library(CytoExploreR)
library(CytoExploreRData)
```

## Save FCS Files
Ensure you have created a folder in your working directory and added your FCS files into it. Use the following commands to save the Compensation and Activation datasets to appropriately named folders:
```R
cyto_save(Compensation, save_as = "Compensation-Samples")
cyto_save(Activation, save_as = "Activation-Samples")
```

## Compensation of Fluorescent Spillover
Prepare compensation controls and compute spillover matrix:
```R
gs <- cyto_setup("Compensation-Samples", gatingTemplate = "Compensation-gatingTemplate.csv")
gs <- cyto_transform(gs, type = "logicle")
cyto_gate_draw(gs, parent = "root", alias = "Cells", channels = c("FSC-A", "SSC-A"))
# More commands...
```

## Analysis of Samples
Analyze the samples (treated samples) by loading and annotating them:
```R
gs <- cyto_setup("Activation-Samples", gatingTemplate = "Activation-gatingTemplate.csv")
# More commands...
```

## Note
For detailed explanation and usage of each command, refer to the comments in the code.
```

This Markdown document provides a structured presentation of the code, including setup instructions, package installation, data processing steps, and analysis procedures.
