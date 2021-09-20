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

3. For the **sequences**, download (right-click, save as..) this [sequence file](/files/1_sequences_fasta.txt), then select it from your computer in the **sequence** section
4. Leave all other parameters unchanged and click **GO**.

    :question:Analyzing the results
>You see now the positions of all matches with the patterns you entered within the upstream sequences of the selected genes. Each line shows a single match, and the different columns indicate respectively:
>- pattern identifier
>- strand on which the match was found (D for direct, R for Reverse)
>- pattern searched for (i.e. the query strings you provided)
>- name of the sequence in which it was found
>- starting position of the match
>- end position of the match
>- match sequence. The matching bases are indicated in UPPERCASES. The 4 flanking bases at left and right are in lowercases.
>- matching score. In this case all scores equal 1

>Notice that positions are returned in negative coordinates, relative to the end of the sequence (the last nucleotide has position -1). This behaviour was selected with the "Origin" option in the dna-pattern form (Origin=end). This option is particularly useful for analyzing regulatory sequences, but it can be inactivated in other cases.    

> You will now display the same results graphically, on a **feature map**.

5.  Click on the **Feature map** button on the bottom of the result page. The results from the previous page have been automatically transferred to this form.
6. In the Title box, type

>Gata boxes and Hap sites in the upstream regions of NIT genes

7. Leave other parameters unchanged and click **GO**.
8. Save the image on your computer.

    :question:Analyzing the results
>After a few seconds, the feature map should appear. A few comments:
>- Gata boxes appear in blue, Hap sites in red
>- Color boxes are displayed either above or below the horizontal black lines, accordingly to the strand of the match.
    
## B : Obtaining a matrix from a database

>You will retrieve the Gcn4 count matrix from the JASPAR database. 
1. In the **Matrix tool** menu, select **retrieve matrix**
2. Select as database **Jaspar**, then as collection **Jaspar core nonredundant Fungi**, then search for **Gcn4**
>The matrix appears in **transfac format**. You may download the file (link **output file**)
3. At the bottom of the page in the "next step" box, click on the button **convert matrix** to automatically send the matrix to this program
4. Run the program to produce a **logo**, if you click on it, you can download the **PDF file** (high-resolution format usable for publications)

![plot](./hands-on/logoExercice1.png)


