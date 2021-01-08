---
title: "Import data into R"
teaching: 20
exercises: 20
questions:
- "How to prepare a csv file for my raw phenotypic data?"
- "How to read a csv file with RStudio?"

objectives:
- "Make your raw phenotypic data in a R friendly way"
keypoints:
- "Ensure your files contain all the required columns from template ."
- "Save your file in csv format"
- ""
---

After growing season, you have your data files downloaded from KnowPulse, the next step, you want to inport your files into Rstudio for further analysis. 


## Step 1
[GAPIT user manual]:(http://www.zzlab.net/GAPIT/gapit_help_document.pdf)
Use the given command to input your phenotype file:
myY <- read.csv("Data_Phenotypes.csv")
DT::datatable(myY)

Use the given command to input your genotype file:
myG <- read.csv("Data_Genotypes.hmp.csv", header = F)
as.tibble(myG[1:10,1:11]) # Map + marker Info

Use the given command to input your covariates+kinship file:
myCV <- read.csv("Results_Add/GAPIT.PCA.csv")
str(myCV)

myK <- read.csv("Results_Add/GAPIT.Kin.VanRaden.csv", header = F)
str(myK)