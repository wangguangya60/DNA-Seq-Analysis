# DNA-Seq-Analysis

### Genome version
* [different GRCh37](https://gatk.broadinstitute.org/hc/en-us/articles/360035890711)
* [human_g1k_v37](ftp://ftp.ncbi.nlm.nih.gov/1000genomes/ftp/technical/reference/human_g1k_v37.fasta.gz)
* [hs37d5](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/technical/reference/phase2_reference_assembly_sequence/hs37d5.fa.gz)
* [GRCh38 or hg38](ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/001/405/GCA_000001405.15_GRCh38/seqs_for_alignment_pipelines.ucsc_ids/GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.gz)
 

## Fastq QC
### QC Tools
* [seqtk fqchk](https://blog.liang2.tw/posts/2015/09/seqtk/)
* [fastqc](https://github.com/s-andrews/FastQC)

## Fastq Mapping
## BAM format
* [supplementary and secondary alignments](https://www.cnblogs.com/timeisbiggestboss/p/8856888.html)
* [SA tag](https://www.biostars.org/p/116201/) indicate chimeric reads (split reads)
## BQSR
* [Process of BQSR](http://zenfractal.com/2014/01/25/bqsr/)，An introduction to how BQSR works.
## Tips about depth statistics - PYSAM
the difference between pysam.depth() and pysam.pileup()

depth: " compute the per-base depth"
mpileup: "the number of reads covering the site" 

depth: bases cover at each position
pileup: reads cover at each position

pileup do much filtering -Q -q -A, while depth does not 

# Tips about depth statistics

## samtools mpileup
* samtools mpileup DEFAULT skip [[UNMAP,SECONDARY,QCFAIL,DUP] and only with [PROPER_PAIR] (this is not written in doc).
* Note: -rf, -ff is not the same as samtools view -r, -f

* samtools mpileup DEFAULT NOT "Double-counting coverage of overlapped read pairs".

## samtools depth
samtools depth DEFAULT skip [[UNMAP,SECONDARY,QCFAIL,DUP]
* samtools depth NOT "Double-counting coverage of overlapped read pairs" if set base quality > 0; or use "-s" parameter.

## samtools bedcov
* samtools bedcov DEFAULT skip [UNMAP,SECONDARY,QCFAIL,DUP]
* samtools multicov provide args for QC,duplicates filtering
* [a post explaining about this](https://www.biostars.org/p/195497/)

## deeptools
* provide fragment coverage, extend paired reads to a whole fragment (proper for peak calling at e.g., nucleosome footprint, TSS, TFBS)

![7dkOV](https://user-images.githubusercontent.com/28535831/169741133-7168fdd1-6fbb-483e-be1f-caf5a023ca03.png)


## Careful about depth of coverage of Overlapping Paired-End Reads
* [samtools mpileup](https://www.biostars.org/p/87299/#284421) count 1x for overlaping position by default, but can count 2x using "-x" (sets overlaping bases quality to zero), so using -Q 1 to filter
* [samtools depth](https://www.biostars.org/p/323047/) counts each mate separately, means 2x, but can using sambamba depth with "--fix-mate-overlaps" to avoid double-counting
## to calculate fragment length
* For [pysam](https://www.biostars.org/p/312885/), using "record.template_length"
* For samtools, using records in the 9th column of a bam

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
