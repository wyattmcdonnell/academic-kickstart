---
title: "Condensing 10x Genomics clonotypes to barcode using tidyverse"
date: 2019-12-21T14:24:45-06:00
draft: false
---
While handling some multiplexed 10x data this past week, I realized that it had been a little while since I'd had to get per-barcode clonotype information to easily add into a [Seurat](https://satijalab.org/seurat/) object or other data format. I've also been using Haynes Heaton's `souporcell` tool and have been very happy with the results, so in this example we'll take some genotype information and concatenate that with our clonotype information. If you haven't read the `souporcell` [preprint](https://www.biorxiv.org/content/10.1101/699637v2), you should do so! The `souporcell` GitHub repo can be found [here](https://github.com/wheaton5/souporcell). Anyways, here's a few lines that will get you where you need to go using `data.table` to read things in and `tidyverse` to quickly shape things:

```
# Import your libraries
library(data.table)
library(tidyverse)

# Import your clonotype data
clonotype <- fread('~/projects/filtered_contig_annotations.csv')

# Import your genotype data
genotype <- fread('~/projects/clusters.tsv')

# Filter your clonotype data
clonotype.filter <- clonotype %>% filter(productive==TRUE) # Keep productive rearrangements
clonotype.filter.again <- clonotype.filter %>% group_by(barcode) %>% mutate(clonotype=paste(cdr3,collapse=',')) %>% select(clonotype) %>% unique() # Collapse CDR3s across chains, keep unique clonotypes, and collapse by barcode

# Neatly table everything
my.clonotypes <- merge(genotype, clonotype.filter.again, by='barcode', all.x = TRUE)

# If you had 3 genotypes mixed in the same lane, here's a quick way to view some of your top clonotypes per genotype
my.clonotypes %>% filter(assignment==0) %>% select(clonotype) %>% table() %>% sort(.,decreasing = TRUE) %>% head()
my.clonotypes %>% filter(assignment==1) %>% select(clonotype) %>% table() %>% sort(.,decreasing = TRUE) %>% head()
my.clonotypes %>% filter(assignment==2) %>% select(clonotype) %>% table() %>% sort(.,decreasing = TRUE) %>% head()
``` 
