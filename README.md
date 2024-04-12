# ChIP-Seq-Analysis

## Biological System
The analysis studies the binding sites of COUP-TFII (also referred to as NR2F2) collected from [GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE52008). ChIP-seq was performed on human endometrial stromal cells (HESC) treated with deciduogenic hormones using an antibody against COUP-TFII. As input, immunoprecipitation with normal rabbit IgG was performed.

![Biological System](image.png)

Precise control of inflammation is crucial for maintaining immune response balance and preventing persistent inflammation. The nuclear factor erythroid 2-like 2 (NRF2), also known as Chicken ovalbumin upstream promoter-transcription factor II (COUP-TFII), plays a vital role in controlling inflammation. When stabilized due to oxidative stress, NRF2 triggers the expression of antioxidants and protective genes, exerting an anti-inflammatory effect crucial for healing. Overactivation or underactivation of NRF2 is implicated in chronic disease development due to its role in regulating inflammatory responses.

NRF2 operates by binding to specific DNA sequences known as antioxidant response elements (AREs), regulating the transcription of genes responsible for antioxidants and detoxification enzymes. This activation aids in combating oxidative stress, maintaining redox balance, and defending against reactive oxygen species. Additionally, NRF2 is involved in cell-fate specification, organogenesis, angiogenesis, and metabolism.

Previous studies in mice have examined NRF2's role in female reproduction, but its role in humans remains unclear. Hence, this experiment was conducted to explore it. NRF2's role in the uterus may shed light on understanding endometriosis, a common disease in women characterized by chronic pelvic pain and progesterone insensitivity. Studies have shown that mice lacking NRF2 down-regulate stromal progesterone receptors, suggesting a role in progesterone resistance in women with endometriosis. Additionally, NRF2 expression is reduced in endometrial stoma of women with endometriosis compared to healthy women, indicating its potential significance in the disease's pathogenesis.

## Experiment Design
Pooled primary human endometrial stromal cells from 6 healthy women were analyzed upon decidualization with a hormone cocktail of cAMP, E2, and medroxyprogesterone acetate. ChIP-seq was performed using antibodies for COUP-TFII (N2RF2). The dataset consists of two samples.

![Experiment Design](image.png)

## ChIP-seq Details
The experiment used the Illumina Genome Analyzer II to obtain sequencing results. Single reads were obtained.

### Downloading the Sample Containing the Antibody and QC (Quality Control)
First, the sample containing the antibody was analyzed. The reads were downloaded in fastq format and underwent quality assessment using the `fastqc` command.

### Aligning the Sequences to the Human Genome (hg19)
The reads were aligned to the human genome (hg19) using Bowtie2. The alignment rate for the sample was 98.54%, indicating successful alignment.

### Analysing the Input File
The same process of downloading data, quality checking, and alignment to the genome was done for the input file (sample without the antibody).

### Peak Visualization with IGV
One of the detected peaks was visualized using IGV. The peak is located in the IGF1R gene, a target gene of the COUP-TFII transcription factor associated with focal adhesion. The visualization indicates a difference in the number of reads between the positive sample and the control (input sample).

### Peak Calling using MACS2
To identify true peaks, MACS2 was used with sorted bam files of the positive and control samples. A p-value of 1e-10 was specified to ensure biologically meaningful peaks.

## Conclusions
The results of ChIP-seq analysis of the TF NRF2 (COUP-TFII) showed that this transcription factor act by directly binding to genes involved in pathways like integrin signalling, VEGF signaling, focal adhesion and cytokine-cytokine receptor interaction. These are related in general to cell adhesion, angiogenesis and inflamation which are hallmarks of endometriosis [1]. This confirms that the transcription factor studied here is involved with the development of the disease. The direct target genes identified by this analysis were also found in the related study [1].

## References
[1] Li X, Large MJ, Creighton CJ, Lanz RB, Jeong JW, Young SL, Lessey BA, Palomino WA, Tsai SY, Demayo FJ. COUP-TFII regulates human endometrial stromal genes involved in inflammation. Mol Endocrinol. 2013 Dec;27(12):2041-54. doi: 10.1210/me.2013-1191. Epub 2013 Oct 31. PMID: 24176914; PMCID: PMC3857200.

[2] Vomund S, Schäfer A, Parnham MJ, Brüne B, von Knethen A. Nrf2, the Master Regulator of Anti-Oxidative Responses. Int J Mol Sci. 2017 Dec 20;18(12):2772. doi: 10.3390/ijms18122772. PMID: 29261130; PMCID: PMC5751370.
