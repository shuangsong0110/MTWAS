# MTWAS: Multi-tissue Transcriptome-Wide Association Studies

MTWAS is an R package for the paper

> Song, S., Wang, L., Hou, L., & Liu, J. S. (2023). Partitioning and aggregating cross-tissue and tissue-specific
genetic effects in identifying gene-trait associations.

## :hammer_and_wrench: Installation

```r
devtools::install_github("szcf-weiya/MTWAS")
```

## :rocket: Get Started

### Train weights

```r
# load TWAS data
data("twas_data")
# select cross-tissue eQTLs
ct.eQTL = select.ct.eQTL(twas_data, verbose = F, ncores = 1)
# select tissue-specific eQTLs
list.ts.eQTL = select.ts.eQTL(twas_data, ct.eQTL = ct.eQTL, ncores = 1)
```

### Association tests

```r
# load summary statistics
data("summary_stats")
# association test
twas.single.trait(summary_stats, twas_data, list.ts.eQTL)
```

Data formats and function details: https://hohoweiya.xyz/MTWAS/articles/mtwas.html
