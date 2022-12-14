# PublicVersion_3C

This repository contains all the files necessary to replicate "Worth the wait? Contextual influences on delaying gratification during the COVID-19 pandemic". 

NOTE: The Loyalty foundation is named "ingroup_foundation" and the Care foundation is named "harm_foundation" throughout the processing and analysis scripts. There are also a handful of variables in the processing script that are not included in the analysis manuscript as they weren't used in the manuscript. The codebook <codebook_20220905.pdf> is included to help with understanding what the variables are in R.  The appendix <measures_appendix_20220905.pdf> contains the measures in their entirety.  Occupation and nationality responses were collected in open response format and were hand-coded by the researchers, based on commonly used categories to group the variables.  

Participants were recruited via CloudResearch, a website that manages Mturk HITs (Human Intelligence Tasks). Data were collected on February 12, 2021 from a sample of 440 individuals in the US, who were paid $2 for completing the study. Data were recorded via Qualtrics. The original dataframe was edited to remove identifiable info before uploading to GitHHub.

For processing, cleaning, and exclusions, you will need the following files: 1. <lookup1MCQ.txt> 2. <lookup2MCQ.txt> 3. <lookup3MCQ.txt> 4. <3C_processing.Rmd> 5. <3C_Live_Study_data.csv>. The <3C_processing.Rmd> file on successfully running will spit out the final data frame for analyses, <omit_df.csv>. The <lookupMCQ.txt> files are used to automatically calculate the temporal discounting/MCQ indices.

For analyses, you will need the following files: 1. <3c_analysis.Rmd> 2. <omit_df.csv>. The  <3c_analysis.Rmd> will run all the analyses needed to replicate the manuscripts results section.

OVERVIEW OF PROCESSING SCRIPT

First, the data is loaded and unnecessary columns are dropped. Some data is excluded based on length of task, either 3x too fast or 3x too slow.  The COVID-19 Delay of Gratification index is calculated next.  More exclusions are calculated next: removing NAs, recording a birth date response, converting characters, ensuring attention checks are passed, and assigning IDs. Indices are calculated next, with final exclusions for folks who were below recommended consistency scores for the temporal discounting measure. Next, reliabilities are calculated. Last, the final dataset is exported.

OVERVIEW OF ANALYSES SCRIPT

First, the final dataset is loaded. A summary stats table is calculated to create the summary stats table on the manuscript and the summary stats for COVID DoG is calculated seperately. Demographics are calculated for the methods, demographics section. Correlation matrices are calculated next for the summary stats table on the manuscript. Next, the hierarchical linear regressions are conducted, followed by the correlation comparisons. Last, some misc. analyses are listed: Age model and a COVID DoG simultaneous model. These misc analyses are not included in the manuscript, but are present incase reviewers are curious. 


