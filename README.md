# Intro to Bioinformatics (ConGen 2021)

## 1. Intro
1.  who we are
2.  purpose of course (take newly learned command line skills and apply them to simple biological data)

---

## 2. Getting the data
1. brief mention of github (https://github.com/goodest-goodlab/good-protocols/tree/main/how-tos/git-basics)
2. cloning the project repo

---

## 3. Project organization
1. Reminder of file systems
2. overview of how we organized this project
3. just generally stress how important organizing your files is

---

## 4. Intro to 'commands' and the Unix philosophy
1. a 'command' is just a chunk of code that interacts with the file system and/or processes formatted text. baby pointing to communicate vs. adults using language metaphor.
2. TEXT files form the basis of data science. formatted text > command > processed formatted text
3. Unix: a command should do one thing and do it really well, commands should be able to work together. vs. Microsoft: a program should focus on doing one thing well, but be able to do all the things (Word for word processing, but can also make tables, edit images, etc., Excel for data analysis but can also edit images and format text, etc., and so on)
4. maybe demonstrate piping and redirection here?
5. since TEXT FILES form the basis of unix commands, being able to interact with them is important: talk about text editors
6. maybe remind them that working remotely on a cluster is literally different but conceptually the same as running commands on your personal computer... and requires different tools
7. talk about our setups briefly

---

## 5. List of common unix commands and their function

---

## 6. Bioinformatics example

Ideas for general tasks:

- We've call structural variants on chromosome 19 of mouse. How many of these overlap with genes?

    1. Need bed file of structural variants, gtf or gff file from mouse
    2. Will use grep and cut to turn gff file into bed file with genes, bedtools intersect to get overlap with SVs, and awk to calculate average overlap
    3. Maybe use samtools or bedtools to extract the sequences? Would need fasta file then, too.

- We've called SNPs on some genome. How many have we called and what is the average quality of these calls? Read depth?

    1. Need VCF file.
    2. Again, using grep, cut, awk to calculate various things. Then maybe bcftools to filter.

---

## 7. Automating commands with scripts
1. just converting the above tasks to a bash script.
2. looping over multiple samples/chromosomes
3. mention gnu parallel, clusters, snakemake to scale things up