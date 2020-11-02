# General feedback

### Comments on working with R Projects, GitHub, and reproducibility

* When working within an R project, you don't have to refer to files by their absolute path name (which will be different for different users) instead you can refer to files by their relative path (which is the same for all users). For example, if the file **mydag.png** is stored in the root folder of your R project, you can include it in a R Markdown file by using the relative path `![]("mydag.png")` rather than an absolute path like `![]("mycomputer/myfolder/hdat9700/assessment1a/mydag.png")` 

* If you create images in an R chunk, R will create a new folder locally within your R project, which is the name of the repo with **files** apprended e.g. `assessment1a_files/`. In order for the images to appear when your assessment markdown file is viewed on GitHub, you need to also add and commit these files. 

* You can supress unwanted code, messages and warnings in your R markdown file using the `echo = FALSE`, `message = FALSE` ad `warning = FALSE` options respectively. These can be set for individual chunks or globally for all chunks (see line 7 in my .Rmd)

* Some matching methods involve an element of randomness. In order to make your results reproducible in these scenarios you can set a seed using `set.seed()` 

* It is good practice to comment your code.

### Comments on presentation and interpretation

* You should only quote decimal places to the degree they are meaningful. An estimated effect of 220g is effectively the same as 22.134g and writing 220g looks more more professional and is easier to read. 

* It is generally insufficient to print statistical output without adding some sort of comment or brief interpretation. 

* Interpretation can be short and in plain language. Interpretative statements work well when they can be linked to some statistical quantity or estimate. For example: 

    > Smoking mums were younger on average (25.3 years versus 27.7 years)
    
    > In the weighted matched data the estimated effect of smoking during pregnancy on birth weight is -258g (95% CI = -303g, -213g), i.e. babies of mothers who smoked were 258g lighter on average.
    

### Question 1 (Draw the DAG) 

* There was no need to restrict the DAG to the limited set of observed variables. The DAG captures our understand of the factors affecting smoking behaviour and birth weight; this understand should be independent of the observed data at hand. We should be able to draw a DAG without any data. 

* To identify the total effect of birthweight you shouldn't close front door paths. For example, if gestational age is presented as a mediator on the path `smoking` &rarr; `gestational age` &rarr; `birth weight` you shouldn't control for gestational age when estimating the effect of smoking on birth weight. 

* It is ok if there were still open backdoor paths on your DAG after controlling for the avaiable variables. 

* If you feel unsure about the concept of closing backdoor paths, try practicing using the app: https://cbdrh.shinyapps.io/backdoor-paths/

### Question 2 (Matching and balance)

* Generally it is a good idea to conduct some exploratory data analysis before diving into the matching step. 

* The matching variables should align with the variables identified to close backdoor paths in Question 1.

* This step is a good example of where it was expected to add some commnet to the statistcal output, rather than just print the summary of the matching process without comment. 

### Question 3 (Fit the models and compare)

* The two models were estimated using separate datasets so comparing model fit wasn't really relevant here, this was not a question of model selection. 

* The key parameter was the estimate for smoking, which is interpreted as either the association between smoking and birth weight, or the causal effect of smoking on birth weight, depending on how confident we are that we have met the criteria to make causal claims from observational data. 

### Question 4 (Limitations and exchangeability)

* Exchangeability is unlikely to hold because a lot of important variables weren't available to balance on. This comes back to the idea in Question 1: it is important to think beyond the observed variables and think about what you would ideally contol for and how unavailable data might affect your estimates.




