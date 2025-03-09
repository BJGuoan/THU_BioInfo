# Week3 Sequence Alignment
## 0. bash操作
使用.sh文件，修改为可执行
第一行写为#!/bin/bash，之后可以写命令，也可以使用变量
变量赋值，等号前后不可加空格，调用文件变量时要在变量名前加$
ifelse要用中括号，内部加空格，最后用fi结束
```
#!/bin/bash
file1=a.txt
head -n 1 $file1
if [ 1 -gt 2 ];then echo Yes; fi
for i in aa bb cc dd; do echo $i; done
```

## 1. Alignment Algorithms
### (1) scoring matrix
- identities + mismatches + gap penalties, show evolutionary relationship artificially
- alignment based on protein is more informative than DNA, aas also need to consider similarities, so use scoring matrix (symmetric/asymmetric)
- gap penalty $W_n = a+(n-1)b$, opening a gap is more expensive than extending it (especially in pr)

### (2) Needleman-Wunsch (global) algorithm
- recursive algorithm uses dynamic programming
- global alignment (align entire sequence), sometimes miss short motifs because they're outweighed by other sequence
- 2-d table, first fill 1 in identical cells, fill 0 in other cells in the most right/down row/col, then fill from right-downward, score = original score in the cell + max score in the previous col/row, finally trace back

### (3) Smith-Waterman (local) algorithm
- search for sub-strings of highest similarity, doesn't require entire sequence similarity
- can start at any position, more complexed

### (4) Application -- BLAST
- given a query sequence, find a match from a database
- NW/SW can do it, but with $O(mn) *$ number of sequences in the database
- heuristic methods -- pre-compute a hash table, lists positions of every possible tuples, then search k-mers when using, use mini-dynamic programming in the gaps of searching
- looks for neighborhood words instead of perfect matches
- output -- raw score, bit score (normalize to length), E-value (multiple testing correction of p), P-value
- blastn, blastp, blastx(pr data, dna query), tblastn(dna data, pr query), tblastx(dna to dna, through pr)

## 2. Conservation Analysis
- start from pairwise alignment, infers shared evolutional history, or similar biological function (conserved sequence usually have conserved functions, but similarity $\not = $ homology)
- homologs, orthologs (from same ancestor, used in tree building), paralogs (from duplication)
- finding orthologs -- bi-directional blast between two genomes, phylogenic analysis, genomic synteny/ gene order
- multiple alignment -- algorithm (BLAST) + model (HMM/SCFG)

## 3. Genomic Projects and Resources
- HGP, ENCODE (encyclopedia), 1000 Genome Project, TCGA (cancer genome atlas), metagenomic projects, ancient DNA, ...
- nc databases -- EMBL/GenBank/DDBJ (browsers -- NCBI, UCSC, Ensembl), RefSeq (annotation)
- pr -- Swiss-Prot, TrEMBL, UniProt
- organism specific database / other specific sub-databases