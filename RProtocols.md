[HOME](./index.html)

## R Protocols     
Tricks of the trade. A compilation of topics I found to be useful while coding in R. Thought I would share them with you all.    

### Plant Breeding & Genetics  
[Heritability](./Rmd Protocols/Heritability.html)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Are we still talking about how to calculate heritability? Yes... yes we are.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It's been a topic in our office for what feels like a month, so I wrote up a small summary & how to calculate H2 in R   
[QTL Analysis](http://rpubs.com/shantel-martinez/ERA8-Mapping)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; I recently published an article that included QTL analysis; follow the entire workflow from data to the [publication](https://www.biorxiv.org/content/10.1101/784652v1.full) figures.     

[GWAS in GAPIT]()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Determining what is the `favorable` allele for your trait based on the + or - effect in GAPIT    
[Genomic Prediction]()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <a href="https://nbviewer.jupyter.org/github/shantel-martinez/shantel-martinez.github.io/blob/master/Rmd%20Protocols/GS_one-step_notes_CNL.html?flush_cache=true" style="color:#8B8378"><b>PHS GS One-step Approach</b></a> rrbLUP five-fold cross-validation broken down and explained in an R markdown notebook

![](https://github.com/shantel-martinez/Lab_Resources/blob/master/example_img/onestep%20vs%20twostep.jpg?raw=true)
<a href="https://nbviewer.jupyter.org/github/shantel-martinez/shantel-martinez.github.io/blob/master/Rmd%20Protocols/GPModelTutorial_20190219.html?flush_cache=true" style="color:#8B7D7B"><b>Five-Fold CV</b></a>    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Two-step approach; rrbLUP, RKHS, and LASSO broken down and explained in an R markdown notebook (<span style="color:#CD5C5C">MISSING reliabilty adjustment</span>)    
> D. Sweeney helped me realize I was doing a two-step GP process initially without adjusting for the reliability. So this meant I was calculating BLUPs for my phenotype data, and those BLUP values were what I was using as a phenotype to calculate the GEBVs.  So I guess (meaning I still need to read more on this), when you do a two-step process, you need to divide your GEBVs by a reliability factor. And this last part, I had not done before.  Which the two-step method is not wrong, however without an adjustment I could be inflating my prediction accuracies.     
> However what I'm working on now, is a one-step approach. The 1 -step approach is using my covariate variables while I am running the mixed.solve command in rrBLUP.   

### Data Visualization   
Want some figure inspiration from R?   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Check out the [tidyverse](https://twitter.com/search?q=%23tidyverse&src=tyah), [dataviz](https://twitter.com/search?q=%23dataviz&src=typd) and [TidyTuesday](https://twitter.com/search?q=%23TidyTuesday&src=tyah) hashtags on Twitter.   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Here is an example of a **#TidyTuesday** I did for Week 20: [step-by-step guide](https://nbviewer.jupyter.org/github/shantel-martinez/shantel-martinez.github.io/blob/master/Rmd%20Protocols/TidyTuesdayWk20.html)   
Join the [Data Visualization Soceity](https://www.datavisualizationsociety.com/)   

### Resources  
[Computing Resources](./Rmd Protocols/CodingShortcuts.html) includes topics such as data management, electronic notebooks, coding shortcuts and links to cheatsheets.     

----------  
[HOME](./index.html) <span style="float:right;">  v2019.12.08  </span>   
