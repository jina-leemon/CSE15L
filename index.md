'Helloo my name is Jinaaaa'
wow I made a bunch of edits and they allll disappeareeed

*I am currently working on blast*

**woohoo**

# Batch Psiblast

## Intro

[psiblast web interface](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastSearch&PROGRAM=blastp&BLAST_PROGRAMS=psiBlast)

![blast_web_output](https://i0.wp.com/ncbiinsights.ncbi.nlm.nih.gov/wp-content/uploads/2019/07/blast_results.png?resize=1108%2C777&ssl=1)

example output:
> FDH98_gp296,YP_008125763,N/A,hypothetical protein CR5_023 [Cronobacter phage CR5],15.228,1.03e-90
FDH98_gp296,AFO71243,N/A,hypothetical protein CR5_023 [Cronobacter phage CR5],15.228,1.03e-90
FDH98_gp296,QVW55183,N/A,hypothetical protein pEaSNUABM29_00139 [Erwinia phage pEa_SNUABM_29],11.293,1.09e-90
FDH98_gp296,QXN70502,N/A,hypothetical protein AGENTSMITH_98 [Bacillus phage vB_BspM_AgentSmith],21.173,1.29e-90

information:
* query accession
* match accession
* protein identity
* p identity
* e value

Using `psiblast` in the BLAST+ suite gives these results

---

Part of the code I used to extract data:
```
class Homology:
    #qseqid sacc sscinames stitle pident evalue
    #e.g) FDH98_gp150 gb|QTH80280.1| Pseudomonas phage pPa_SNUABM_DT01 putative UvsX protein [Pseudomonas phage pPa_SNUABM_DT01] 39.407 0.0
    def __init__(self, sacc, sscinames, stitle, pident, evalue):
        #gb|QTH80280.1|
        self.sacc = sacc
        #Pseudomonas phage pPa_SNUABM_DT01
        self.sscinames = sscinames
        #putative UvsX protein [Pseudomonas phage pPa_SNUABM_DT01]
        self.stitle = stitle
        #39.407
        self.pident = pident
        #0.0
        self.evalue = evalue
```
