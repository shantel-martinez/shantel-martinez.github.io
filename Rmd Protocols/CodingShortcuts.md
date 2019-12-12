

## Computing Resources 

### Electronic Lab Notebook (ELN)

Great [article](https://www.nature.com/articles/d41586-018-05895-3?utm_source=twt_nnc&utm_medium=social&utm_campaign=naturenews&sf195296490=1) on getting started with an electronic notebook.
A [Nature article](https://www.nature.com/articles/d41586-018-07196-1?tm_source=twt_nnc&utm_medium=social&utm_campaign=naturenews&sf201140318=1) about why so many scientists love Jupyter Notebook (I am biased, I know).

------

### Resources found while on the hunt for something

How to output nice tables in R: a [list of packages](https://community.rstudio.com/t/output-nice-looking-formatted-tables/1084) and [5 package tutorials](https://htmlpreview.github.io/?https://github.com/ropenscilabs/packagemetrics/blob/master/inst/examples/tableGallery.html)
A compare and contrast of [how the Economist presents their data figures](https://medium.economist.com/mistakes-weve-drawn-a-few-8cdd8a42d368).

------
## Online Coding Cheatsheets 

### Simple cheat sheets for markdown:

[Github Wiki](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) | [Github markdown](https://help.github.com/en/categories/writing-on-github)| [md Basics](https://www.markdownguide.org/basic-syntax/) | [Typora document](http://support.typora.io/Markdown-Reference/) | [R md document](https://bookdown.org/yihui/rmarkdown/html-document.html)
K. Broman has a great blog (is that what you call it?) on [R Markdown](https://kbroman.org/knitr_knutshell/pages/Rmarkdown.html)

### Simple cheat sheets for Jupyter Notebook:

[Jupyter Notebook shortcuts](http://maxmelnick.com/2016/04/19/python-beginner-tips-and-tricks.html)
Datacamps Jupyter and R markdown [cheatsheet](https://datacamp-community-prod.s3.amazonaws.com/48093c40-5303-45f4-bbf9-0c96c0133c40)

------

*If recently unused, I often forget these coding commands or shortcuts and I have to google search them again. Instead, I just keep my running list of forgotten favorites listed here*

### Git 

*All research files are backed up onto GitHub*
`git pull origin master` : Updates this computers master folder with changes from the other computer
`git status` : Tells you what has changed since the last push
`git add -u` : This tells git to automatically stage tracked files -- including deleting the previously tracked files.
    OR `git add /folder` to add a whole specific folder of changes
`git commit -m 'enter commit comment here'`
`git push origin master`
   *Enter in user name (email) and password*

### Anaconda 

*Use the Anaconda terminal to access Jupyter Notebook*
`cd /d D:`
`cd /d General\ Research\ Files/`
`jupyter notebook` This will start Jupyter Notebook in the web browser
   *Notebooks are found in the `/Lab notebook/` folder*

### Jupyter 

*Shorthand keys*
`Shift-Enter` run cell, select below
`Ctrl-Enter` run cell
`Alt-Enter` run cell, insert below
`M` to markdown (remember to esc from edit mode) `Y` to code

### Markdown 

`Green Text`: Green Text
`Red Text`: Red Text
`Blue Text`: Blue Text
*Colors only work when the md output is html ex: github pages or jupyter notebooks*

`<a id="abbr_name"></a>`: Header link()[#abbr_name]: Reference Header Link&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: Tab 6 spaces

`<div style="text-align: right"> [TOC](#TOC) </div>`

`--------------` creates a line break

### Typora 

`Ctrl+/`: Source Code Mode
`Ctrl+Shift+-`: Zoom Out
`Ctrl+Shift+=`: Zoom In

### R 

`colnames(k)<- sub("X","",colnames(k))` replace column name characters like X or V with nothing. This is useful when importing data tables and R formats the empty column names.

`c("#F8766D", "#7CAE00", "#00BFC4","#C77CFF")` : default ggplot2 colors
2
`length(df[!is.na(df)])` Tells me how many values in the df are NOT NA. you can also specify col `df$col`

`CV <- subset(CNLM, GID %in% myCVc$taxa)` Subsetting CNLM with similar GID as myCV taxa, There are 1059 GID in common
`PCC<- merge(myCVc,CV,by="ID")` merge columns by two columns with the same name
`names(myCVc)[14] <- "GID"` rename column 14 only
`PHSred7$GIDx <- with(PHSred7,paste("cuGS",PHSred7$GID,sep=""))` Make dfGID ### to dfGID ### to dfGIDx cuGS### by adding a new row
`PHSwhite$GIDx <- gsub("cuGSOH", "OH", PHSwhite\$GIDx)` replace cuGSOH in column GIDx with OH.

**lme4**
`VarName` : Fixed Effect
`(1|VarName)`: Random Effect; random intercept with fixed mean
`x + (x|VarName)`: Random Effect; correlated intercept and slope with the fixed effect `x`
`(1|Env%in%GID)`: Random effect interaction; GID within Env

**Rounding** [adapted from KBroman](https://kbroman.org/knitr_knutshell/pages/Rmarkdown.html)
If you want and ouput value of 0.70, and don’t want to see 0.7035597 ... you can use `r round(cor(x,y), 2)` or `r sprintf("%.2f", cor(x,y))` but its, of course, not perfect.
Broman's solution to this problem was to create a function `myround` in my R/broman package `library(broman)`. Now you can write `r myround(cor(x,y), 2)` and it would give 0.70 or -0.001 in the way that you want.
