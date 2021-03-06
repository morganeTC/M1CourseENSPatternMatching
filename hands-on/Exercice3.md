# Exercice 3 : Matrix-based pattern matching

## A : Search for a motif described as a matrix

You will scan the upstream region of the gene **even-skipped (eve)** from the _Drosophila melanogaster_ genome with 12 matrices, representing the binding specificity of 12 factors that are known to regulate this gene. The aim is to locate the putative binding sites for these 12 factors.

You will follow in part this protocol: "Using RSAT to scan genome sequences for transcription factor binding sites and cis-regulatory modules" by Turatsinze, Thomas-Chollier et al, Nature Protocols (2008). Although not recent, the theoretical aspects are still valid. The PDF is not open-access, it is available on Moodle.

1. Open the article, read the **Introduction** until "Procedure"
2. Read **Box 1** and **Box 2**
>matrix-scan allows a wide range of analyses, but is slow. For the prediction of TFBS, RSAT now offers a faster program called matrix-scan-quick that you will use today. 

3. In the **Pattern matching** menu, select **matrix-scan (quick)**
4. Fill the **sequences** by providing the [upstream sequence (5500bp) of the eve gene](/files/2_eve_upstream_fasta.txt) (download on your computer first)
5. The **Matrix** section allows specifying the transcription factor-binding motif(s). For the even-skipped study case, the [matrix file is in Transfac format](/files/3_oreganno_eve_12_matrices.txt). Copy/paste the file with the 12 matrices in the Matrix box. In the menu Matrix format, **select 'transfac**'.
6. The next section of the form provides several options for specifying the **background model** (the statistical model for the sequences that do not correspond to instances of the motif). The choice of the background model crucially affects the results. For first analysis, select **Markov chain order 0**.
7. Check the option **organism-specific**, and select _Drosophila melanogaster_ and **upstream-noorf**.
8. The section **Scanning options** determines the scanning mode and the parameters to return. The selector **Origin** specifies whether the origin for reporting coordinates should be the end or the start of the sequences. By default, the **end** is considered as the origin, so that the hits are reported with negative coordinates for upstream sequences.
9. Select **return sites + pval** to compute the p-values associated to each predicted site.
10. Defining a **threshold** on the **P-value** is the preferred approach. Set the value to **1e-4**
11. Click **GO**.

    :question:Analyzing the results
>How many predictions do you obtain for these factors ? Given the p-value threshold, how many false positives do you expect in this region ? 

12. Then produce the **feature map**. For the option **color file**, provide [this file containing RGB color codes](/files/4_eve_color_file.txt). It ensures that the factors always have the same colors on the graphs.
13. Save the figure   

    :question:Analyzing the results
>Compare your figure with Figure 8a (top) presenting the annotated TFBS. Do your predictions seems correct ?
>Are you missing some (=false negative) or finding more (= potential false positives) ?
    
## B : Estimating the amount of false positives

You will estimate the amount of false positives by re-running the exact same analysis, but using as input random sequences generated according to a realistic background model.
In this random control case, the matches you will obtain are all false-positives (ie sites that are predicted to be a TFBS but that connot be since you are working with artifical non-biological sequences).
>Start by generating the random sequences. 

1. In the **Build control sets** menu, select **random sequences**
2.  For the **sequence length** : 5500 (same length as the eve upstream region)
3. Number of sequences : **10** 
4. In the **Background** section, select the background model that will serve to produce the random sequence. Choose _Drosophila melanogaster_ for the organism. Keep oligonucleotide size to **6** to use a Markov background model of order 5 (read Box 3 for details on Markov models).
5. Click on **Go**
6. Save the generated sequence file
7. Redo steps 3-13 above (only for threshold 1e-4), using this set of **random sequences as input** (step 4) 

    :question:Analyzing the results
>How many predictions do you obtain for these factors ?
>Does that correspond to the expected number of false-positives ? 

:fast_forward: The protocol also presents random controls in the form of **randomly selected regions**, which are biological sequences instead of artificial ones. Other controls like permuting the matrices are also common in research projects. If you're interested to go further, the protocol also presents the search for regulatory modules (CRERs).  
