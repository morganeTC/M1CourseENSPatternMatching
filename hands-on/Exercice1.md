# Exercice 1 : motif descriptors

The goal of this first exercice is to manipulate different motif descriptors: **consensus sequences** and **count matrices**.
You will use the program **convert-matrix** from the RSA-tools suite. This tool allows to :

    Perform interconversions between various matrix formats
    Produce consensus and regular expression descriptors
    Calculate various statistics on the PSSMs
    Reverse PSSMs
    Permute PSSMs
    Construct logos

As input data, you will construct a matrix **from a multiple alignment**, and also fetch a count matrix from the **JASPAR database**. The matrices describes the binding motifs of transcription factors seen in the course (**Meis and Gcn4**). 

## A : Constructing a personal matrix

1. Go to the [RSAT teaching server](http://pedagogix-tagc.univ-mrs.fr/rsat/)
2. In the **Matrix tool** menu, select **convert matrix**

>You will construct a count matrix for the factor Meis, from the multiple alignment of TFBS extracted from various vertebrate genomes. The alignment is in FASTA format. Note that the tool allows to convert to a wide range of formats.

3. Copy the following alignement in the matrix box, and select as format **sequences**

    ```\>1
    TGACAA
    >2
    TGACAG
    >3
    TGATGG
    >4
    TGACAA
    >5
    TGGCAG
    >6
    TGATTG
    >7
    TGACAG
    >8
    TGACAG
    ```
4. The **background model** is not used in this exercice, you can leave the default option
5. Click on **Go** to run the program with default parameters

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


