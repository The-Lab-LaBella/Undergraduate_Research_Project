# Undergraduate Research Project

## Introduction

In this project, we will test the hypothesis that **co-expressed genes have similar codon usage bias**.

To do this, we will use standard machine learning analyses, primarily focused on random forest classification. Throughout the semester, we will work our way through the analysis below. 

## Background

### The Yeasts

Yeasts are typically defined as single cellular fungi. Across the fungal subphylum, however, there have been multiple transitions to and from single-celled fungi. Therefore, the "yeasts" do not form a single group. When we use the word "yeast," we refer specifically to the yeast of the Saccharomycotina subphylum.

In our google drive, please read the "Who are the Yeasts" PDF to learn more about who the yeasts are and why they are so cool.

### Codon Usage Bias

Codon usage bias is the unequal use of synonymous codons within or between genes and genomes. We now know that some codons are decoded into amino acids faster and more efficiently than other codons. We refer to these as **optimal** codons. We hypothesize that the codon content of genes is a key feature for co-regulation. 

Read more about codon usage bias here: https://github.com/The-Lab-LaBella/Intro_to_codon_usage

We will be focusing on a codon usage metric called **Relative Synonymous Codon Usage (RSCU)**. It is a measure of how much our observed codon frequencies deviate from what we would expect if codon usage was random. 

For example, there are 4 valine codons (GTT, GTC, GTA, GTG). If our gene has 100 valine amino acid sites, we expect that there will be 25 of each of the codons. 

If we observe that there are 45 GTT codons instead, this would be more than we expect. To calculate the RSCU, we divide the observed number by the expected number: 45/25 = 1.8. 

If we observe that there are 20 GTT codons, this would be less than we expect. The RSCU would be 20/25 = 0.8

If we observe that there are 25 GTT codons, this would be what we expect. The RSCU would be 25/25 = 1.

If we observe that there are 0 GTT codons, the RSCU would be 0/25 = 0.

If we observe all the codons (100) are GTT, the RSCU would be 100/25 = 4.  

Therefore, an RSCU value of 1 suggests random codon usage. An RSCU value of >1 suggests a preferred codon. An RSCU value of <1 suggests an unpreferred codon. The maximum value for each codon is the total number of synonymous codons, which ranges from 1 (for Methionine and Tryptophan) to 6 (Leucine, Serine, Arginine) 


### KEGG modules

KEGG is a database that helps us understand the possible functions of genes we identify in genomes. One component is KEGG Ontologies or KEGG IDs. These are assigned to genes based on sequence similarity to a reference sequence. 

![image](https://github.com/user-attachments/assets/c78cd4a6-2c26-4d9e-a021-93d2544fcf6e)

In this example you can see that genes assigned a KEGG ID K17100 have the function: _dihydroxyacetone synthase_. The **Symbol** category is a general abbreviation for this type of gene. You can also see in the **Genes** section that this gene has been found in multiple species, including the yeast _Scheffersomyces stipitis_ (PIC). In the species _S. stipitis_ the gene is known as DHA1. 

You can find all of the species abbreviations here: https://www.genome.jp/kegg/tables/br08606.html

You can also see that this gene belongs to a module that can represent all the steps of a pathway or reaction. Read more about the types of modules here: https://www.genome.jp/kegg/module.html

![image](https://github.com/user-attachments/assets/b78428be-f24c-4459-bbfe-d7c639f671e9)

This is the module in which the KEGG genes are assigned to 17100 functions. You can see that this is involved in the formaldehyde assimilation/xylulose monophosphate pathway. The circles represent various compounds and the squares starting with R0 are the reactions. 

### Random Forest

Random forests are powerful machine-learning methods that are also relatively simple. To learn more about random forest methods see this video https://www.youtube.com/watch?v=J4Wdy0Wc_xQ 


## Experiment

### Preliminary evidence

Our hypothesis is that we can distinguish module genes from each other based on codon usage. Preliminary support for this hypothesis is seen in the figure below. 

![image](https://github.com/user-attachments/assets/6c24e74f-19dd-4848-b280-4ef9ec098a52)

Genes within the urea (M0029) and galactose (M00632) pathways are more similar in RSCU across all degenerate codons to genes within the pathway (mean difference 0.351 and 0.335 for urea and galactose) than between the two pathways (mean difference 0.351). 


### Setting up R

We will start this experiment in R. Make sure you have RStudio installed on your computer https://rstudio-education.github.io/hopr/starting.html

We will use a format in R called R-Markdown. For an introduction to R-markdown see:
https://www.youtube.com/watch?v=asHhuHRxhvo

For a complete guide to R-markdown see: https://bookdown.org/yihui/rmarkdown/

### Running your first analysis 

I have created an R-markdown file that will introduce you to the analysis of 1 species for 1 module. We will expand this analysis over the course of the semester.


