# Exercice 2 : String-based pattern matching

The goal of the second and third exercices is to learn how to search for a known motif within a DNA sequence of interest.
This technique is here applied to predict transcription factor binding sites (TFBS), but it may be applied to search for other biological signals such as exon/intron boundaries, restriction sites... From the RSA-tools suite, you will use the programs:

- **dna-pattern** with motifs described as consensus sequences => Exercise 2
- **matrix-scan** with motifs described as matrices => Exercise 3

You will also learn to estimate the rate of false positive predictions and use appropriate controls to evaluate your results. 

## A : Search for a motif described as a consensus sequence

You have a list of upstream regions of a selection of nitrogen-responding genes in the yeast, you will search the positions of putative GATA boxes and Hap sites within these regions of 800bp.
This exercice is adapted from the Tutorial of the program dna-pattern, accessible from the RSAT website at the bottom of the tool form. 

1. In the **Pattern matching** menu, select **dna-pattern**
2. In the **Query pattern(s) box**, you will enter the patterns to be searched for. Each pattern must come on a separate line. The first word of each line is the string description of the pattern, the second word is an identifier for this pattern. Type the following text in the Query pattern(s) box:

>GATAAG	  Gata_box

>CCAAY	  Hap_site

Note the use of degenerate IUPAC degenerate code: the Y from CCAAY on the second line means "either C or T".

3. For the **sequences**, download this [sequence file](/files/1_sequences_fasta.txt), then select it from your computer in the **sequence** section
4. Leave all other parameters unchanged and click **GO**.

    :question:Questions
    >Compare the computed matrix with the one you made manually during the course.
    Look at the consensus sequence under the matrix. Is it strict or degenerate ? Compare it with the one you made manually during the course.
    Have a look at the logo, note how the height in each column is different.
    
6. Go back to the previous page, rerun the program by choosing as **output format transfac**

    :question:Questions
    >The transfac format is very different from the tab format used before. What is the main difference ?
    This is the format used by the TRANSFAC database ; this format is used by many bioinformatics tools, and has the advantage of integrating a name and identifier (ID and AC fields) within the matrix format.
    
## B : Obtaining a matrix from a database

>You will retrieve the Gcn4 count matrix from the JASPAR database. 
1. In the **Matrix tool** menu, select **retrieve matrix**
2. Select as database **Jaspar**, then as collection **Jaspar core nonredundant Fungi**, then search for **Gcn4**
>The matrix appears in **transfac format**. You may download the file (link **output file**)
3. At the bottom of the page in the "next step" box, click on the button **convert matrix** to automatically send the matrix to this program
4. Run the program to produce a **logo**, if you click on it, you can download the **PDF file** (high-resolution format usable for publications)

![plot](./hands-on/logoExercice1.png)


