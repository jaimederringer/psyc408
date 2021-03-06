---
title: How to Read a GWAS
---

# How to Read a GWAS

## Logic

A genome-wide association study (GWAS, pronounced "GEE-wah-s") is an exploratory method for discovering correlations between any one of many (often millions) of available genotyped variants (usually single-nucleotide polymorphisms, SNPs, pronounced "snips") and a phenotype of interest. It follows the process of (literally) checking each variant in turn for correlation with the phenotype. Because of this massive "multiple testing" problem, we adjust the typical threshold for statistical significance (p < 0.05) for the equivalent of 1 million tests (that is, we divide 0.05 by 1 million); so a statistically significant result in a GWAS usually requires p < 5 x 10^-8. (We do not divide by the total number of tested SNPs even if it is >1 million - up to 17 million tests is now common - because the tests are not independent. That is, linkage disequilibrium means many tests are highly correlated, so it's like doing the exact same test over and over again, where the result is guaranteed to be the same, so we don't count it against the multiple testing burden.) Beyond evaluating whether there are significant associations observed, there are a variety of common ways that papers use to summarize the (millions of) results.

## Participants

Because of the large number of tests, and the low threshold for statistical significance, and the anticipated small effect of any one SNP, we need a very large sample to detect any of these effects as statistically significant. (P-values are the result of a function depending on both the effect size AND the sample size - so if we're looking for small p-values, we need either large effects - which we don't expect in genetics - or a large sample.) For normal-range phenotypes (ie. anything not restricted to cases of extreme, severe, rare outcomes), which is the vast majority of work in behavior genetics, we typically need sample sizes over 100,000 participants for adequate "power" to detect our anticipated reasonable effect sizes as being statistically significant.

Take note of any specific participant characteristics as well. Was the same limited to a certain ancestry group? (Most work so far has relied on samples of European ancestry; more research is now emerging in other ancestry groups in the past few years, but papers do still typically restrict to a single narrowly defined ancestry group.) Also note if they're looking at only males or only females, or to a certain age group. This can inform how we interpret the phenotype and results.

## Phenotype(s)

How have the researchers operationalized (defined, measured) their phenotype of interest? Does it seem reasonable (face validity)? Are there any concerns that they might not be measuring well what they're trying to understand? 

## Common tables & figures

**Manhattan plot:** This will be included in >95% of all GWAS you encounter. It is a way to summarize the results of the millions of tests that have been performed. (see Figure 1 in the Day et al. 2018 reading.) The horizontal x-axis is a map of the genome, organized from left to right by chromosome, and within chromosome by location. Each dot represents a single tested SNP. The vertical location of the SNP along the y-axis is its p-value for the correlation of itself with the phenotype - but in Manhattan plots, the p-values are negative-log-transformed (that's the -log10(p) label on the y-axis) so that SMALLER values are HIGHER on the plot. Basically, statistically significant SNPs are jumping up, saying "Look at me!". There is usually a horizontal dotted line provided at the level of statistical significance (again, usually p < 5x10^-8) so you can visually see where in the genome (by chromosome location) the statistically significant SNPs are located. Occasionally you will see a circular Manhattan plot; these are the same, except they are harder to read. People who use circular Manhattan plots are wrong.

**QQ Plot:** These are falling out of fashion, but see the example we used in the Population Genetics & Ancestry lecture. The x-axis is the distribution of p-values under the null (assuming no effects, but randomly occurring low p-values due to multiple testing alone). The y-axis is the observed distribution of p-values across all tests. If the dots (again, representing each tested SNP) fall along the diagonal, then there is not statistically significant effects more than would be expected by chance. If there is "lift-off" from the diagonal (and the GWAS methods specify that ancestry principal components were included as covariates), then those SNPs have lower p-values than would be expected by chance alone.

**Barplots summarizing evidence:** There are a wide variety of follow-up analyses that can be done using the GWAS results. Barplots are commonly used to summarize these results. Because the metrics can vary widely, it's important to read the text to figure out what the axes are indicating. Usually, higher bars mean that thing/label is more "important"/strongly represented by lower p-values within the GWAS results.

## Effect Sizes

NOTE: A p-value is not an effect size. It is the result of a function depending on both the effect size AND the sample size. A low p-value may occur either because there is a large effect OR because the sample size is large. 

*Always*

**Largest genetic effect:** Depending on the paper, this may be presented in the text, or it may be buried in the supplement. Because of consistently small individual effect sizes, many papers now restrict reporting of individual SNP effects to summary depictions, such as the Manhattan and QQ plots, and provide a limited table of "top results", or even a full table of millions of results, in the supplement. Usually, the effect size of a single SNP is reported in terms of its odds ratio (OR; for a binary yes/no outcome) or its correlation (r) or standardized regression weight (beta) (for continuous outcomes). Another commonly used effect size reporting metric is often labeled variance explained (r^2 - conveniently, the square of what the correlation metric would be).

*After the individual SNP results, there is a MULTITUDE of ways that the set of results may be summarized. Some common approaches are:*

**Polygenic scores:** Aggregation of genome-wide variants, summed like items on a test. Usually reported in terms of correlation (r) or variance explained (r^2). We know that effect sizes of polygenic scores tend to be inflated by parallel cultural transmission processes - the strongest test of a polygenic score is WITHIN FAMILIES (that is, how well does it correlate with phenotype differences within a family, eg. between siblings, where ancestry/cultural confounds are controlled). Under NO CIRCUMSTANCE should a polygenic score be tested in the exact same sample in which the SNP effects (GWAS) were estimated - this leads to CATASTROPHIC overestimation of the effect (eg. it's not hard to get r^2 = 1.0, because the number of variables is greater than the number of participants, so "overfitting" to the sample is a BIG problem).

**Heritability among unrelated participants:** As we discussed in the Twin Studies lecture, the logic of twin studies can be extended to "unrelated" folks who have been genotyped, where we can ask the same question: to what extent are more closely related (more genetically similar) individuals more similar in their phenotypes? 

**Genetic correlation with other phenotypes:** Just like we can estimate correlations between observed phenotypes, so we can estimate the extent to which the pattern of results in a GWAS is similar to patterns of GWAS results observed for other phenotypes. Genetic correlation is typically scaled to range from 0.0 to +/- 1.0, REGARDLESS of the observed phenotypic correlation and the observed heritabilities of the phenotypes (so, even if the observed phenotypes are weakly correlated and/or weakly heritable, they can still show a high degree of genetic correlation, indicating that what phenotypic correlation/heritability there is can be traced to similar patterns of associated SNPs. Because most GWAS results these days are shared publicly in-full, it is relatively easy to take results from a single GWAS and estimate genetic correlation with any GWAS that has ever been done, without needing access to the underlying data (that is, the method requires only the results/summary statistics).

**Gene-based or Pathway analyses:** Evaluation of whether p-values are lower than would be expected by chance within certain pre-defined sets of SNPs, such as individual genes or "pathways" (sets of multiple genes that share some common function, such as "dopamine genes" or "skeletal genes" or "genes expressed in the brain"). This is one of the RARE EXCEPTIONS to the "p-value is not an effect size" rule - most gene- or pathway-tests ONLY give a p-value as the result. The paper will usually tell you what the adjusted threshold for statistical significance is here - it will depend on the number of genes/pathways tested. Keep in mind that ONLY pre-defined genes/pathways CAN be tested - so it cannot test what we don't yet know.

**Tissue/expression enrichment:** There are a huge, rapidly developing array of methods for examining tissue expression and epigenetic mechanism "enrichment," or (as in the gene- or pathway-based methods) overrepresentation of SNPs with low p-values in regions known to be expressed in certain tissues or known to be susceptible to variations in expression from a variety of factors (including but not limited to methylation, which is one commonly studied form of epigenetic modification).

## Themes

As you're reading the paper, consider which commonly addressed themes (from the papers below) apply or are discussed. Take note of which themes the results support, and which if any they contradict. Recognizing these themes across different papers will help synthesize the information. 

* Plomin, R., DeFries, J. C., Knopik, V. S., & Neiderhiser, J. M. (2016). Top 10 replicated findings from behavioral genetics. Perspectives on Psychological Science, 11(1), 3-23. <https://doi.org/10.1177/1745691615617439>
* Briley, D. A., Livengood, J., Derringer, J., Tucker-Drob, E. M., Fraley, R. C., & Roberts, B. W. (2019). Interpreting behavior genetic models: seven developmental processes to understand. Behavior Genetics, 49(2), 196-210. <http://publish.illinois.edu/dabriley/files/2018/11/Briley-2018-Interpreting-behavior-genetic-models.pdf>

## Replications?

One common "gold" standard for evidence in science is replication. Many GWAS include internal replication samples (that is, a smaller sample set aside specifically for the purpose of replicating any newly observed effects). You can also use Google Scholar to look for replications (either successful or null) by clicking on the "cited by" link below the paper's search listing (any replication attempt will cite the original study). Keep in mind that science is slow, so new papers (especially < 2 years old) may not yet have any available replication attempts reported, successful or otherwise.
