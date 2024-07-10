# DP-DFT

This contains Python codes used in our experiments on methods for privately releasing the top K significant SNPs using Discrete Fourier Transform (DFT).

We conducted experiments based on simulation and real data to evaluate the accuracy and run time of our methods. The distribution of the statistics for the experiments can be found in the Simulation Data files. 

Supplement.pdf contains detailed proofs of our theorems and some explanations of the data used in our experiments.

## Important Note

・The assumption in our original paper "the original $k$-th element $g_k$ cannot be recovered from the reconstructed $k'(\neq k)$-th element $\hat{g}_{k'}$" might be too rough. More precisely, we should assume "the sorts in neighboring datasets are indistinguishable based on the probabilities of outputting the same $K$ elements" (In the paper, we briefly mention this before Theorem 1). (I updated the proof in Supplements.pdf.) (Can we really say that this assumption is reasonable?)  
← This assumption is based on that the original $g$ cannot reconstructed from $g' = \mathrm{IDFT}(\mathrm{PAD}^m(\mathrm{DFT}^s(g)))$. Further exploration of this assumption is needed, and depending on the results, our method could be of significant high utility.

## Future Directions

・Developing better ways to set the parameter $s$.

・Evaluating the relationship among elements of the reconstructed vector in DFT rigorously (and answering to the above question in Important Note).

・This study aimed to output the top $K$ data, but if sorting process certainly has privacy issues when using DFT, our method would be useless. (cf. When using the Laplace mechanism, there is no problem at all with sorting before adding noise. Quantifying the change in privacy assurance when sorting might be an important research question.) Instead, if the values reconstructed by IDFT can be regarded as statistics, our method can be used for the purpose of accurately publishing statistical information. Therefore, it may be worthwhile to consider statistical tests using elements of the reconstructed vector.

・Considering genome dependencies and its effects on the changes in statistics (vector) (Analyzing local sensitivity might be useful.).

・We should perform some pre-processing, like constructing a pseudo-statistics vector similar to the original vector. 
(Then, based on the constructed vector, we can conduct similar procedures to our algorithms.)

・Utilizing our methods (idea) in other research fields, for example, histogram publication (where the number of varying elements (of the vector) between neighboring datasets is limited). <---- It would be easy to employ our methods because there is no need to sort and the ${\it sensitivity}$ analysis is simple. (Further reseach and experiments are needed for each domain, though.)

## Note

For details of our mechanisms, please see our paper entitled "Efficient and Highly Accurate Differentially Private Statistical Genomic Analysis using Discrete Fourier Transform" (https://doi.org/10.1109/TrustCom56396.2022.00078) presented at IEEE TrustCom 2022.

Errata:

・p.527. Definition 4. " $D_i, D'_i \in \mathcal{D}^M$ " → " $D, D' \in \mathcal{D}^M$ "

・p.528, l.6. The sentence "In this study, we assume that the original $k$-th element $g_k$ cannot be recovered from the reconstructed $k'(\neq k)$-th element $\hat{g}_{k'}$." should be ${\it deleted}$. 

・p.529. Algorithm 4. Step 10. "steps 5 and 6" → "steps 8 and 9"

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
