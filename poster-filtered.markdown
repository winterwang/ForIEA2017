---
title: "Changing trends in the prevalence of _H. pylori_ infection in Japan (1908-2003): a systematic review and meta-regression analysis of 170,000 individuals"
author: Chaochen Wang^1^, Takeshi Nishiyama^1^, Shogo Kikuchi^1^, Manami Inoue^2^,  Norie Sawada^2^, Shoichiro Tsugane^2^, Yingsong Lin^1^
email: "abelardccwang@gmail.com"
institute: | 
    | 1 Department of Public Health, Aichi Medical University, Nagakute, Aichi, Japan; 
    | 2 Epidemiology and Prevention Group, Center for Public Health Sciences, National Cancer Center, Tokyo, Japan
longinstitute: "Aichi Medical University"
web: "winterwang.github.io"
logo: "images/lg.png"
#backimg: "images/logo.png"
bibliofiles: "bib/bib.bib"
posteroptions: width=90,height=140,scale=1.2 #,grid # portrait
#posteroptions: width=110,height=90,scale=1.2 #,grid # landscape
headerheight: 18cm
colorstyle:
# large, Large, LARGE, huge, Huge, veryHuge, VeryHuge, VERYHuge
titlefont: size=\huge,series=\bfseries
authorfont: size=\LARGE
institutefont: size=\LARGE
knit: (function(input, encoding, make = TRUE) { source('tex/makefile-renderer.R', local = TRUE) })
---




[columns=2]

[column]

# BACKGROUND

-  Gastric cancer burden remains high in Japan, approximately 50,000 deaths/year in Japan (2nd leading cause of cancer deaths).

-  Evidence supports a central role for _H. pylori_ in the development of upper-gastrointestinal diseases, including peptic ulcer and noncardia gastric cancer.

-  Cross-sectional studies have suggested that the prevalence of _H. pylori_ infection increases with age, while the whole picture remains obscure.

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

- The PRISMA statement for preferred reporting of systematic reviews and meta-analyses was used as a guide to conduct this study. (Fig.1. Flowchart of Study Selection) 

- **PubMed ** ("Helicobacter"[Mesh] OR "Helicobacter pylori"[title/abstract]) AND ("Prevalence"[Mesh] OR "prevalence"[title/abstract]) AND ("Japan"[Mesh] OR "Japan"[title/abstract] OR "Japanese"[title/abstract])

- **EMBASE **  ("prevalence"/exp OR prevalence:ab, ti) AND ("Japan"/exp OR "Japan: ab, ti" OR "Japanese: ab, ti") AND ("helicobacter"/exp OR "helicobacter pylori": ab, ti) AND (humans)/lim.

- We also scrutinised the reference lists, and searched for unpublished data by contacting the head of known ongoing study projects in Japan. 

- The risk-of-bias assessment was independently performed by two authors (LY and WC) using the Joanna Briggs Institute Prevalence Critical Appraisal Tool。

![Flowchart of Study Selection](images/Figure_1.png)

# STATISTICAL ANALYSIS (1)

- Prevalence by birth year were extracted from 45 studies (273 data points).

- Penalized cubic spline was used to model the prevalence as a function of birth year in the framework of generalized additive mixed model (GAMM) implemented in the `mgcv` package in R. 

[column]

# STATISTICAL ANALYSIS (2) 

- Pre-specified explanatory variables included in the meta-regression were as follows:   
  Study ID, birth year, population source (community-based or clinical-based), diagnostic testing (serological test, or others; others: urinary assays, salivary assays, stool antigen tests, and gastric biopsy), types of ELISA kits for measuring _H. pylori_ positivity (antigen derived from domestic or foreign strains), and data collection period (prior to the year 2000, or later than 2000), with **study ID as a random effect** and **other variables as fixed effects**.

- Observations weighted by the inverse of the sum of the within-study variance and the residual between-study variance using the `meta` package.



# RESULTS

![Multivariable adjusted prevalence of _H. pylori_ infection in Japanese by birth year.](images/main.png)

# Take-home message

- `R bookdownplus` is an extension of `bookdown` for academic and literal writing, especially for reproducible reports.

- `R bookdownplus` is still being developed. Feel free to join me either in contributing templates to [**my Github repo**](https://github.com/pzhaonet/bookdownplus) ^[https://github.com/pzhaonet/bookdownplus], or in writing the tutorial of R bookdownplus [@R-bdp].

<!--\vskip0.5cm

[/columns]


[columns=2]

[column]

-->

# COI Declaration



\vskip1.5cm


# Bibliography

\printbibliography

<!--\vskip4.4cm-->

[/columns]
