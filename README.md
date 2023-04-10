# DP-DFT

This contains Python codes used in our experiments on methods for privately releasing the top K significant SNPs using Discrete Fourier Transform (DFT).

We conducted experiments based on simulation and real data to evaluate the accuracy and run time of our methods. The distribution of the statistics for the experiments can be found in the Simulation Data file. 

Supplement.pdf contains detailed proofs of our theorems and some explanations of the data used in our experiments.

## Important future directions

・Developing better ways to set the parameter s.

・Evaluating the relationship among elements of the reconstructed vector in DFT rigorously. (The assumption in this study that "the original $k$-th element $g_k$ cannot be recovered from the reconstructed $k'(\neq k)$-th element $\hat{g}_{k'}$" is too rough.)

・Considering genome dependencies and its effects on the changes in statistics (vector) (In practical terms, this might cause little problems. Analyzing local sensitivity might be useful.).

・We should perform some pre-processing, like constructing a pseudo-statistics vector similar to the original vector. 
(Then, based on the constructed vector, we can conduct similar procedures to our algorithms.)

・Utilizing our methods (idea) in other research fields, for example, histogram publication (where the number of varying elements (of the vector) between neighboring datasets is limited).

## Note

For details of our mechanisms, please see our paper entitled "Efficient and Highly Accurate Differentially Private Statistical Genomic Analysis using Discrete Fourier Transform" (https://doi.org/10.1109/TrustCom56396.2022.00078) presented at IEEE TrustCom 2022.

Errata:

・p.529. Algorithm 4. Step 10. "steps 5 and 6" → "steps 8 and 9"

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
