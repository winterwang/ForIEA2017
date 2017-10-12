---
title: "Changing trends in the prevalence of _H. pylori_ infection in Japan (1908-2003): a systematic review and meta-regression analysis of 170,572 individuals"
author: Chaochen Wang^1^, Takeshi Nishiyama^1^, Shogo Kikuchi^1^, Manami Inoue^2^,  Norie Sawada^2^, Shoichiro Tsugane^2^, Yingsong Lin^1^
email: "abelardccwang@gmail.com"
institute: | 
    | 1. Department of Public Health, Aichi Medical University, Nagakute, Aichi, Japan; 
    | 2. Division of Cohort Consortium Research, Center for Public Health Sciences, National Cancer Center, Tokyo, Japan
longinstitute: "Aichi Medical University"
web: "winterwang.github.io"
#logo: "images/lg.png"
#backimg: "images/logo.png"
bibliofiles: "bib/bib.bib"
posteroptions: width=90,height=155,scale=1.2 #,grid # portrait
#posteroptions: width=110,height=90,scale=1.2 #,grid # landscape
headerheight: 19.5cm
colorstyle:
# large, Large, LARGE, huge, Huge, veryHuge, VeryHuge, VERYHuge
titlefont: size=\Huge,series=\bfseries
authorfont: size=\huge
institutefont: size=\LARGE
knit: (function(input, encoding, make = TRUE) { source('tex/makefile-renderer.R', local = TRUE) })
---



```
## Warning: package 'ggplot2' was built under R version 3.4.2
```

```
## Warning: package 'knitr' was built under R version 3.4.2
```

[columns=2]

[column]

# BACKGROUND

-  Gastric cancer burden remains high in Japan, with approximately 50,000 deaths/year (2nd leading cause of cancer deaths).

-  Evidence supports a central role for _H. pylori_ in the development of upper-gastrointestinal diseases, including peptic ulcer and noncardia gastric cancer.

-  Studies have suggested that the prevalence of _H. pylori_ infection increases with age; however, this phenomenon is presumably due to a birth-cohort effect.

-  We systematically reviewed the existing literature that presented estimates of the prevalence of _H. pylori_ infection in the Japanese population.

-  The obejectives are:  
   a) to derive a robust prevalence estimate of _H. pylori_ infection by birth year;   
   b) to clarify whether _H. pylori_ infection exhibits a birth-cohort pattern. 

<!--

- Standard abreviations \\eg and \\ie for \eg and \ie
- Units like \pps{900}
- **Highlights** and *highlights*

-->

# DATA SOURCES AND SEARCH STRATEGY

- The PRISMA statement for preferred reporting of systematic reviews and meta-analyses was used as a guide to conduct this study. (Fig 1. Flowchart of Study Selection) 

- **PubMed: ** ("Helicobacter"[Mesh] OR "Helicobacter pylori"[title/abstract]) AND ("Prevalence"[Mesh] OR "prevalence"[title/abstract] OR "infection rate") AND ("Japan"[Mesh] OR "Japan"[title/abstract] OR "Japanese"[title/abstract])

- **EMBASE: **  ("prevalence"/exp OR prevalence:ab, ti  OR "infection rate"/exp OR "infection rate": ab, ti) AND ("Japan"/exp OR "Japan: ab, ti" OR "Japanese: ab, ti") AND ("helicobacter"/exp OR "helicobacter pylori": ab, ti) AND (humans)/lim.

- We also scrutinised the reference lists, and searched for unpublished data by contacting the head of ongoing projects. 

- The risk-of-bias assessment was independently performed by two authors (Y.L. and C.W.) using the [**Joanna Briggs Institute Prevalence Critical Appraisal Tool**](http://joannabriggs.org/assets/docs/critical-appraisal-tools/JBI_Critical_Appraisal-Checklist_for_Prevalence_Studies.pdf)^[http://joannabriggs.org/assets/docs/critical-appraisal-tools/JBI_Critical_Appraisal-Checklist_for_Prevalence_Studies.pdf].

\center
\includegraphics[width=890pt]{images/Figure_1.png}

\caption{Figure 1. PRISMA Flowchart of Study Selection}

# STATISTICAL ANALYSIS (1)

- More details on how to estimate prevalence of _H. pylori_ by birth year can be found [**here**](https://winterwang.github.io/For_Inoue_pylori/)^[https://winterwang.github.io/For_Inoue_pylori/].

- Prevalence by birth year was extracted from 47 studies (300 data points).

- Observations were weighted by the inverse of the sum of the within-study variance and the residual between-study variance using the `meta` package.



[column]

# STATISTICAL ANALYSIS (2) 
- Penalized cubic spline was used to model the prevalence as a function of birth year in the framework of generalized additive mixed model (GAMM) implemented in the `mgcv` package in R. 

- Pre-specified explanatory variables included in the meta-regression were as follows:   
  Study ID, birth year, population source (community-based or clinical-based), diagnostic testing (serological test, or others; others: urinary assays, salivary assays, stool antigen tests, ^13^C-urea breath test, and gastric biopsy), types of ELISA kits for measuring _H. pylori_ positivity (antigen derived from domestic or foreign strains), and data collection period (prior to the year 2000, or later than 2000), with **study ID as a random effect** and **other variables as fixed effects**.



# RESULTS

- Details/characteristics of the studies included in the current meta-regression analysis are available [**online**](http://rpubs.com/winterwang/288338)^[http://rpubs.com/winterwang/288338].

- Summary of the results of risk of bias diagnosis is available [**here**](http://rpubs.com/winterwang/riskofbias)^[http://rpubs.com/winterwang/riskofbias].

\center
\caption{Figure 2: Multivariable adjusted prevalence of \textit{H. pylori} by birth year}
\includegraphics[width=1200pt]{images/Figure2Rev.png}





\begin{table}[]
\captionof{Table 1. Estimated prevalence of \textit{H. pylori} infection by birth year}
\small
\centering
%\caption{My caption}
%\label{my-label}
\begin{tabular}{p{10cm}p{10cm}p{8cm}p{8cm}}
\toprule
\textbf{Birth year} & \textbf{Prevalence} & \textbf{95\% Low} & \textbf{95\% High} \\ \midrule
1908                & 0.597               & 0.543             & 0.649              \\
1909                & 0.603               & 0.553             & 0.651              \\
1910	              & 0.609               & 0.563	            & 0.654  \\
...                 & ...              & ...            & ...             \\
1925                & 0.674               & 0.657             & 0.690               \\
1926                & 0.675               & 0.659             & 0.690               \\
\rowcolor[HTML]{FFCB2F} 
1927                & 0.675               & 0.660              & 0.690               \\
1928                & 0.675               & 0.660              & 0.688              \\
...              & ...              & ...            & ...             \\
1950                & 0.582               & 0.574             & 0.590               \\
...              & ...              & ...            & ...             \\
1990                & 0.138               & 0.121             & 0.157              \\
...              & ...              & ...            & ...             \\
1996                & 0.087               & 0.070              & 0.108              \\
1997                & 0.081               & 0.064             & 0.102              \\
\rowcolor[HTML]{FFC702} 
1998                & 0.076               & 0.058             & 0.098              \\
...              & ...              & ...            & ...             \\
2002                & 0.057               & 0.039             & 0.082              \\
2003                & 0.053               & 0.035             & 0.078              \\ \bottomrule
\end{tabular}
\end{table}

# CONCLUSION

- Prevalence of _H. pylori_ infection exhibits **a birth cohort effect** in Japan, with prevalence decreasing steadily in individuals born in successive years, **from 58.2% in 1950 to 13.8% in 1990**.  

- Given the fact that the birth-cohort pattern of _H. pylori_ shapes the trends of gastric cancer over time, our findings help to inform screening efforts aimed at prevention and early detection of gastric cancer in Japan.


<!--\vskip0.5cm

[/columns]


[columns=2]

[column]

-->

# COI Declaration:

The authors have no conflict of interest with any corporate organizations relating to this presentation.


<!--\vskip4.4cm-->

[/columns]
