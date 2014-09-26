class: center, middle

# An Integrated Network in Ovarian Cancer

Andrew Quitadamo

---
background-image: url('logo.jpg')

#Overview

* We created an integrated gene and miRNA network using ovarian cancer data from The Cancer Genome Atlas

--

* We expanded an initial network of miRNA eQTLs by including miRNA targets and protein-protein interactions

--

* Extends earlier work in miRNA eQTLs [1]

#####[1] Quitadamo A, Lin F, Tian L, Shi X. "A microRNA-Gene Network in Ovarian Cancer from Genome-Wide QTL Analysis”. Bioinformatics Research and Applications: 10th International Symposium, ISBRA 2014, Zhangjiajie, China, June 28-30, 2014: Proceedings 8492 388 2014. Springer.

---

#Ovarian Cancer

* Ovarian cancer is responsible for ~5% of cancer deaths in women  

--

* There will be an estimated 21,980 new cases and 14,270 deaths from ovarian cancer in 2014. 

--

* The 5 year survival is ~44%, but when ovarian cancer is diagnosed in the first stage the 5 year survival is over 90%.

---

#micro RNAs

* miRNAs are small non-coding RNAs

--

* miRNAs regulate mRNA expression by degrading transcripts or blocking translation

--

* Changes in miRNA expression have been implicated in many cancer types, including ovarian cancer

---

#eQTL Analysis

* Expression quantitative trait loci analysis measures how gene expression is affected by genetic loci

--

* In this case we looked at miRNA expression effection mRNA expression

--

* We used Matrix eQTL, an R package, to perform the analysis [2]

--

* We also used MtLasso2G, which uses a graph based lasso method, to perform a second parallel eQTL analysis [3]

  
#####[2] Shabalin A.A: Matrix eQTL: Ultra fast eQTL analysis via large matrix operations. Bioinformatics 28 no. 10 (2012): 1353-1358.  
#####[3] Chen X, Shi X, Xu X, Wang Z, Mills RE, Lee C, and Xu J: A Two-Graph Guided Multi-task Lasso Approach for eQTL Mapping. Journal of Machine Learning Research (JMLR) W&CP 22:208-217. 
---

# Thinking with Networks

* Our approach combines three different types of biological networks: miRNA-gene targets, protein-protein interactions, and gene correlation networks

--

* Each network incorporates information about different biological mechanisms

--

* By combining the networks to create an integrate network, we hope to generate a more inclusive view of the biology of ovarian cancer

---
# Workflow

<center><img src = "miRNA_int_net_workflow_crop.jpg" style="width: 42%; height: 42%"/><center/>

---

# Results

* 44 miRNA eQTLs, containing 16 unique miRNAs and 44 unique genes

--

* 310 miRNA targets from TarBase [4], 244 could be used as DAPPLE [5] inputs

--

* 145 direct connections from DAPPLE containing a seed gene with a corrected p-value of < 0.05 
 
--

* From MtLasso2G we added 9 correlated miRNAs and 18 correlated genes

--

* Added 8 eQTLs from MtLasso2G

--

* Final network has 167 nodes and 277 edges

--

#####[4] Papadopoulos GL, Reczko M, Simossis VA, Sethupathy P, Hatzigeorgiou AG: The database of experimentally supported targets: a functional update of TarBase. Nucleic Acids Res 2009, 37 (Database issue):D155-8.

#####[5] Rossin EJ, Lage K, Raychaudhuri S, Xavier RJ, Tartar D, IIBDGC, Cotsapas C, Daly MJ: Proteins Encoded in Genomic Regions Associated with Immune-Mediated Disease Physically Interact and Suggest Underlying Biology. PLoS Genetics 2011, (1): e1001273
---

#Final Network

<center><img src = "final_network_corr_mt_crop.jpg" style="width: 85%; height:86"/><center/>

---

#Subnetwork

<center><img src = "final_subnetwork_crop.jpg" style="width: 100%; height:100"/><center/>


---

# Cancer Genes and miRNA

* In the integrated network there were 26 cancer associated genes, 11 of which were associated with ovarian cancer

--

* There were 14 cancer associated miRNAs, 12 related to ovarian cancer

--

* *ESR1* has been indicated as a predictor of ovarian cancer survival

--

* Increased hsa-miR-200c expression has been associated with increased survival, decreased relapse, and increased sensitivity to paclitaxel

---

## Future Work

* Add more networks such as gene regulatory networks

--

* Look at up and down regulatory effects in the network

--

## Acknowlegements

Shi Lab

- Dr. Xinghua Shi

- Benika Hall

- Lu Tian

- Dahlia Shvets

- Dahlia Shvets

- Heena Desai

- Shel Burkes
