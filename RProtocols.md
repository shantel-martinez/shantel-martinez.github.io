[HOME](./index.html)

## R Protocols     
Tricks of the trade. A compilation of topics I found to be useful while coding in R. Thought I would share them with you all.    

### Plant Breeding & Genetics  
[Heritability](./Rmd Protocols/Heritability.html)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Are we still talking about how to calculate heritability? Yes... yes we are.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It's been a topic in our office for what feels like a month, so I wrote up a small summary & how to calculate H2 in R   
[QTL Analysis](http://rpubs.com/shantel-martinez/ERA8-Mapping)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; I recently published an article that included QTL analysis; follow the entire workflow from data to the [publication](https://www.biorxiv.org/content/10.1101/784652v1.full) figures.     

[GWAS in GAPIT](./Rmd Protocols/GAPITAllele.html)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Determining what is the "favorable" allele for your trait based on the + or - effect in GAPIT    

### Data Visualization   
Want some figure inspiration from R?   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Check out the [tidyverse](https://twitter.com/search?q=%23tidyverse&src=tyah), [dataviz](https://twitter.com/search?q=%23dataviz&src=typd) and [TidyTuesday](https://twitter.com/search?q=%23TidyTuesday&src=tyah) hashtags on Twitter.   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Here is an example of a **#TidyTuesday** I did for Week 20: [step-by-step guide](https://nbviewer.jupyter.org/github/shantel-martinez/shantel-martinez.github.io/blob/master/Rmd%20Protocols/TidyTuesdayWk20.html)   
Join the [Data Visualization Soceity](https://www.datavisualizationsociety.com/)   

### Resources  
[Computing Resources](./Rmd Protocols/CodingShortcuts.html) includes topics such as data management, electronic notebooks, coding shortcuts and links to cheatsheets.     

### Genomic Prediction  
![](https://github.com/shantel-martinez/Lab_Resources/blob/master/example_img/onestep%20vs%20twostep.jpg?raw=true)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://nbviewer.jupyter.org/github/shantel-martinez/shantel-martinez.github.io/blob/master/Rmd%20Protocols/GPModelTutorial_20190219.html?flush_cache=true" style="color:#8B7D7B"><b>Five-Fold CV</b></a> Two-step approach; rrbLUP, RKHS, and LASSO broken down and explained in an R markdown notebook (<span style="color:#CD5C5C">MISSING reliabilty adjustment</span>)    
> D. Sweeney helped me realize I was doing a two-step GP process initially without adjusting for the reliability. So this meant I was calculating BLUPs for my phenotype data, and those BLUP values were what I was using as a phenotype to calculate the GEBVs.  So I guess (meaning I still need to read more on this), when you do a two-step process, you need to divide your GEBVs by a reliability factor. And this last part, I had not done before.  Which the two-step method is not wrong, however without an adjustment I could be inflating my prediction accuracies.     
> However what I'm working on now, is a one-step approach. The 1 -step approach is using my covariate variables while I am running the mixed.solve command in rrBLUP.   

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <a href="https://nbviewer.jupyter.org/github/shantel-martinez/shantel-martinez.github.io/blob/master/Rmd%20Protocols/GS_one-step_notes_CNL.html?flush_cache=true" style="color:#8B8378"><b>PHS GS One-step Approach</b></a> rrbLUP five-fold cross-validation broken down and explained in an R markdown notebook

[Bandwidth Parameter for RKHS](https://nbviewer.jupyter.org/github/shantel-martinez/shantel-martinez.github.io/blob/master/Rmd Protocols/BandwidthParameter_RKHS.html?flush_cache=true)
**RKHS**: Based on genetic distance and a kernel function with a smoothing parameter to regulate the distribution of QTL effects. Effective for detecting nonadditive gene effects.

When I was trying to understand modeling using Reproducing Kernel Hilbert Spaces (RKHS), I also needed to understand the parameters being used by the model in `BGLR`. This lead me down a rabbit hole of defining a bandwidth parameter `h` for my datasets.  
> **NOTE1:** I am still in the process of fully understanding `h` and RKHS, so my thoughts and process so far are shown in the R notebook (above link), however it will evolve as I better understand `h` and read more articles.  
> **NOTE2:** I had a meeting with the statistical consulting group and both the advisor and I went down another rabbit hole of determining the bandwidth parameter for RKHS. But, there is hope!  
>> i) people are *still* working out how to best identify your optimal bandwidth parameter, so at least I am not alone.  
>> ii) some papers that are useful are [Campos et al., 2010](https://www.cambridge.org/core/journals/genetics-research/article/semiparametric-genomicenabled-prediction-of-genetic-values-using-reproducing-kernel-hilbert-spaces-methods/2B823916CF4D76FAE6BC81455FD73ABB), [Pérez-Elizalde et al., 2015](https://doi.org/10.1007/s13253-015-0229-y), and [Peres and Campos, 2014](http://www.genetics.org/content/198/2/483)  
>> "The bandwidth parameter of the Gaussian kernel can be chosen using either cross-validation (CV) or Bayesian methods. From a Bayesian perspective, one possibility is to treat h as random; however, this is computationally demanding because the RK needs to be recomputed any time h is updated. To overcome this problem de los Campos et al. (2010) proposed using a multikernel approach (named kernel averaging, KA) consisting of: (a) defining a sequence of kernels based on a set of values of h, and (b) fitting a multikernel model with as many random effects as kernels in the sequence." - [Peres and Campos, 2014](http://www.genetics.org/content/198/2/483)  

----------  
[HOME](./index.html) <span style="float:right;">  v2019.12.08  </span>   
