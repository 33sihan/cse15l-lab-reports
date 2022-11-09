# Researching Commands
I choose command `grep` to develop 9 examples.

Here are three *command-line* options.

---

##  grep -h

`grep -h` can dispay the matched lines, but do not display the filenames.

Why it is useful:
It is convenient for us to just check the contents of a file without showing the filenames. In this case, if we want to extract sentences with a term, we can use grep -h, which can save a lot of time for us.


**1. Example 1**

**Command:** 
```
grep -h "biomedical" technical/biomed/*.txt 
```

**Output:**
```
The availability of biomedical literature in electronic
        study aimed at enabling the biomedical community to cope
        of biomedical research. These include, but are by no means
        types of ligands could therefore have important biomedical
        biomedical framework. While the SR method has been used in
        biomedical literature [ 3 ] . With the recent development
        Other biomedical databases that include CAM literature,
        international journals [ 5 ] . For biomedical disciplines
        another level of biomedical data integration in which array
          Creators of biomedical databases use terminologies to
        biomedical data sets. Public comment is welcomed.
        33 34 ] . This model has been widely applied in biomedical
        study increases the biomedical significance of findings
        to biomedical education, investigation and industry. For
        biomedical research community. GoMiner is flexible both
        gene annotations or concepts from the biomedical
```

**2. Example 2**

**Command:** 
```
grep -h "mathematical modeling" technical/plos/*.txt
```
**Output:**
```
School of Public Health. The forecast, based on mathematical modeling, was published in the
        to Impact,” Salomon and colleagues use mathematical modeling to assess the epidemiologic
        Salomon and colleagues used mathematical modeling to assess the effect of changing
        The authors have demonstrated through mathematical modeling that the integration of
```
**3. Example 3**

**Command:** 
```
grep -h "UNITED STATES" technical/government/About_LSC/*.txt
```
**Output:**
```
SUPREME COURT OF THE UNITED STATES
UNITED STATES, PETITIONER 99-960 v. CARMEN VELAZQUEZ ET AL.
ON WRITS OF CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR
SUPREME COURT OF THE UNITED STATES
UNITED STATES, PETITIONER 99-960 v. CARMEN VELAZQUEZ ET AL.
ON WRITS OF CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR
SUPREME COURT OF THE UNITED STATES
CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR THE SECOND
UNITED STATES COURT OF APPEALS
```

##  grep -l
`grep -l` can dispay list of filenames only.

Why it is useful:
It is useful since we can find the exact file from the filenames to get the contexts of these files, which allow us to further discover the details ralated to the term we are looking for.

**1. Example 1**

**Command:** 
```
grep -l "biomedical" technical/biomed/*.txt 
```
**Output:**
```
technical/biomed/1471-2105-3-16.txt
technical/biomed/1471-2105-3-17.txt
technical/biomed/1471-2164-3-7.txt
technical/biomed/1472-6807-1-1.txt
technical/biomed/1472-6882-1-12.txt
technical/biomed/1472-6882-3-3.txt
technical/biomed/1472-6920-2-3.txt
technical/biomed/1472-6947-3-5.txt
technical/biomed/1472-6947-3-8.txt
technical/biomed/1475-9276-1-3.txt
technical/biomed/1477-7827-1-54.txt
technical/biomed/gb-2001-2-4-research0012.txt
technical/biomed/gb-2003-4-4-r28.txt
technical/biomed/gb-2003-4-7-r46.txt
```
**2. Example 2**

**Command:** 
```
grep -l "mathematical modeling" technical/plos/*.txt
```
**Output:**
```
technical/plos/journal.pbio.0020053.txt
technical/plos/pmed.0020039.txt
```
**3. Example 3**

**Command:** 
```
grep -l "UNITED STATES" technical/government/About_LSC/*.txt
```

**Output:**
```
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
```
##  grep -n
`grep -l` can dispay matched lines and their line numbers.

Why it is useful:
It is useful when we want to look the relevant contents about the sentence containing that term. We can utilize line numbers to directly find the sentence, which saves a lot of time for us to accurately locate the sentences. For example, we can easily find and read the paragraphs that contain the sentences.

**1. Example 1**

**Command:** 
```
grep -n "biomedical" technical/biomed/*.txt 
```
**Output:**
```
technical/biomed/1471-2105-3-16.txt:16:        The availability of biomedical literature in electronic
technical/biomed/1471-2105-3-17.txt:526:        study aimed at enabling the biomedical community to cope
technical/biomed/1471-2164-3-7.txt:8:        of biomedical research. These include, but are by no means
technical/biomed/1472-6807-1-1.txt:17:        types of ligands could therefore have important biomedical
technical/biomed/1472-6882-1-12.txt:472:        biomedical framework. While the SR method has been used in
technical/biomed/1472-6882-3-3.txt:22:        biomedical literature [ 3 ] . With the recent development
technical/biomed/1472-6882-3-3.txt:49:        Other biomedical databases that include CAM literature,
technical/biomed/1472-6920-2-3.txt:214:        international journals [ 5 ] . For biomedical disciplines
technical/biomed/1472-6947-3-5.txt:49:        another level of biomedical data integration in which array
technical/biomed/1472-6947-3-8.txt:56:          Creators of biomedical databases use terminologies to
technical/biomed/1472-6947-3-8.txt:624:        biomedical data sets. Public comment is welcomed.
technical/biomed/1475-9276-1-3.txt:143:        33 34 ] . This model has been widely applied in biomedical
technical/biomed/1477-7827-1-54.txt:695:        study increases the biomedical significance of findings
technical/biomed/gb-2001-2-4-research0012.txt:532:        to biomedical education, investigation and industry. For
technical/biomed/gb-2003-4-4-r28.txt:493:        biomedical research community. GoMiner is flexible both
technical/biomed/gb-2003-4-7-r46.txt:75:        gene annotations or concepts from the biomedical
```
**2. Example 2**

**Command:** 
```
grep -n "mathematical modeling" technical/plos/*.txt
```
**Output:**
```
technical/plos/journal.pbio.0020053.txt:9:        School of Public Health. The forecast, based on mathematical modeling, was published in the
technical/plos/pmed.0020039.txt:41:        to Impact,” Salomon and colleagues use mathematical modeling to assess the epidemiologic
technical/plos/pmed.0020039.txt:54:        Salomon and colleagues used mathematical modeling to assess the effect of changing
technical/plos/pmed.0020039.txt:98:        The authors have demonstrated through mathematical modeling that the integration of
```
**3. Example 3**

**Command:** 
```
grep -l "UNITED STATES" technical/government/About_LSC/*.txt
```
**Output:**
```
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:5:SUPREME COURT OF THE UNITED STATES
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:9:UNITED STATES, PETITIONER 99-960 v. CARMEN VELAZQUEZ ET AL.
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:10:ON WRITS OF CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:5:SUPREME COURT OF THE UNITED STATES
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:9:UNITED STATES, PETITIONER 99-960 v. CARMEN VELAZQUEZ ET AL.
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:10:ON WRITS OF CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt:5:SUPREME COURT OF THE UNITED STATES
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt:8:CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR THE SECOND
technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt:5:UNITED STATES COURT OF APPEALS
```
