# DNA-Seq-Analysis
## Fastq QC
### QC Tools
* [seqtk fqchk](https://blog.liang2.tw/posts/2015/09/seqtk/)
* [fastqc](https://github.com/s-andrews/FastQC)

## Fastq Mapping
## BQSR
* [Process of BQSR](http://zenfractal.com/2014/01/25/bqsr/)，An introduction to how BQSR works.
## Tips about depth statistics
the difference between pysam.depth() and pysam.pileup()

depth: " compute the per-base depth"
mpileup: "the number of reads covering the site" 

depth: bases cover at each position
pileup: reads cover at each position

pileup do much filtering -Q -q -A, while depth does not 

samtools bedcov  skip duplicates
samtools multicov provide args for QC,duplicates filtering

[a post explaining about this](https://www.biostars.org/p/195497/)


##
- ABCD
收款方式看
    - DEf
        路径发来说是离开三  
        sfsla
       - 234
       说法加了撒可富
## Coverage Bias
* [Characterizing and measuring bias in sequence data](https://genomebiology.biomedcentral.com/articles/10.1186/gb-2013-14-5-r51)
* [stratification-bed-files](https://github.com/ga4gh/benchmarking-tools/tree/master/resources/stratification-bed-files)
* [tetoolkit](https://github.com/mhammell-laboratory/tetoolkit), Analyse transposable element in genome. [Transposable elements drive widespread expression of oncogenes in human cancers](https://sci-hub.tw/10.1038/s41588-019-0373-3)

## Good Blogs or Websites
* [Helix blog](https://blog.helix.com/blog/)


## Copy number variants
* [CNVkit](https://github.com/etal/cnvkit)

## Bentchmarking
* [scikit-allel](https://scikit-allel.readthedocs.io/en/stable/stats/mendel.html), a toolkit for genome variation analysis and visualization
* [scikit-allel Author's blog](https://alimanfoo.github.io/)

## Exome
* [CCDS GRch37](ftp://ftp.ncbi.nih.gov/pub/CCDS/archive/Hs37.3/)
* [ensembl](http://asia.ensembl.org/Homo_sapiens/Gene/Summary?db=core;g=ENSG00000221957;r=19:54832676-54848569) a useful database for search gene and exome coordinate
