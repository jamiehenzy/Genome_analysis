THIS SYLLABUS IS SUBJECT TO MINOR CHANGES BEFORE THE SEMESTER BEGINS

**BIOL 2406: Computational Tools for Genome Analysis**

Molecular biology has become a big-data science. The wealth of sequencing data currently available holds keys to pressing issues in the life sciences such as the relationship between genotype and phenotype in complex traits; evolutionary dynamics of pathogens and their hosts; and rare variants involved in disease. This course will introduce concepts and skills needed to productively ask questions of genomic data and move toward participating in research projects that involve large sequencing data sets. Topics include: accessing genomic databases, working with large datasets on a computing cluster, navigating and writing scripts with Unix commands, and working with basic R packages to analyze and visualize genomic data, all while implementing good data practices. While knowledge of coding is not a prerequisite, a fearless attitude toward computers is an asset!

_Prerequisites_: Can be taken concurrently with BIOL 2301 

_Learning objectives_. Upon completion of the course, students will be able to:
+ Access and download various types of sequencing data from a variety of databases
+ Understand file structure and organize files and data in a Unix environment
+ Use basic Unix commands to parse and perform operations on high-throughput data files
+ Work with large amounts of data on Northeastern's high-performance computing cluster
+ Write simple scripts to handle multiple files and complex computing tasks
+ Map reads to a genome and analyze variants
+ Use RStudio to perform differential gene expression analysis on RNA-seq data
+ Perform a basic phylogenetic analysis
+ Generate various types of plots to display genomic data
+ Design basic A to Z workflows for common genomic analyses 
+ Understand and implement "best practices" in computational research

_Format_: In-person. Each session will contain some lecture/discussion to introduce concepts, followed by lots of hands-on exercises working with various tools, as in a workshop. During the lecture portion, please keep your laptops closed.

_Material_: 
+ GitHub: readings and other material for the course is on my GitHub site
+ Canvas: a schedule of the class sessions is in Modules on the Canvas site
+ Laptop: please bring one to each class, but use it only during "workshop" portion.

Submission of work: Each student will set up a Github account. Additionally, you'll have an account on NU's "Explorer cluster". Some components of assignments will be submitted to Github and others to the cluster, as per the instructions specific to that assignment.

_Attendance_: This course is formatted as a workshop and is similar to language courses in that you'll be learning the new languages UNIX and R and using them to write scripts, requiring frequent practice and use of your new "words". Additionally, computational work involves a lot of troubleshooting which is best done in the company of others who may be facing the same annoying snags and can help work through them. Therefore, attendance is an important component of the course and counts for 20% of the grade. Beginning with our 3rd meeting, attendance is scored through completion (not correctness) of in-class quizzes/worksheets. Everyone is generously allowed three absences, no questions asked (exam day is an exception). The three absences include Wellness Days and any other personal absences, whether due to illness, accident, or bad hair. Any absence beyond the allotted, however, will result in a zero for that day.

_AI use_: Personally, I'm tremendously excited about the possibilities offered by AI, while also wary of the downsides, and I look forward to experimenting with its use in this class, with you! We will have frequent conversations during the term about ways in which AI is useful for our work, and ways in which it can lead us astray. For purposes of this experiment, please document your uses of AI and share them in class. The objective is to use AI to make us smarter and not dumber!

_Grading_: 	Timely and successful completion of five modules 	50%
			In-class demo (1 solo, 1 with partner)				10% 
			In-class daily quizzes (23, drop lowest 3)			20%
			Exams (in-class + takehome final) 					20%

Due dates for assignments and quizzes:
1  UNIX_HPC		Mon Sep 28
2  Explore!		Mon Oct 19
3  RStudio		Thu Nov 5
Quiz 1, in-class	Mon Nov 23	
4  DGE workflow	Mon Nov 30
5  Phylogenomics	Thu Dec 10

Quiz 2, take-home	Thu Dec 17 – due

Grades are determined according to this chart showing the absolute minimum percentages necessary for each grade:

 

_Assignments_
**UNIX/HPC**: Upon completion you'll be very comfortable working on the command line and navigating the structure of your file system and that of the high-performance computing cluster, “Explorer”. You'll also set up a Github account to use as a portfolio for your work.

**Explore!**: High-Performance Computing refers to a cluster of interconnected computers that supply memory and processing power far beyond what your laptop or desktop provides. Anyone who works with genomic datasets needs to know how to interact with such a system to run analyses on large datasets. You'll learn to navigate the system and use various tools to explore and analyze sequences. You’ll align sequencing reads to a reference genome and find variants -- the spice of life-- involved in disease and evolution!

**RStudio**: Whole suites of R packages have sprung up to allow researchers to do bioinformatics in R. In this assignment, you'll learn how to use the various features of RStudio efficiently to prepare yourself for the fun to come in the remaining three assignments.

**DGE**: Differential gene expression analysis is a required tool in the transcriptomics tool kit. You'll perform this type of analysis start-to-finish on a couple of datasets, including actual data generated by a Northeastern U researcher. This assignment is the crown jewel of the set!

**Phylogenomics**: Many insights into evolution and disease can be gained from comparing sequences of homologs, so much so that a whole subfield of "phylogenomics" (or phylogenetics) developed on the coattails of sequencing technology. You'll learn how to perform simple phylogenetic analyses in R. 

Below is a rough idea of the topics we'll cover from session to session. However, I'll post details for each session in Canvas Modules as we progress through the semester.

#	Date	Topics
1	Thu Sep 10	Course introduction; Command line setup, best practices; Github accounts
2	Mon Sep 14	UNIX basic commands
3	Thu Sep 17	Writing bash scripts; file permissions
4	Mon Sep 21	Regular expressions; FASTQ files
5	Thu Sep 24	Intro to Explorer: nodes and directories
6	Mon Sep 28	Using modules on explorer
7	Thu Oct 1	Running jobs on cluster: SLURM
8	Mon Oct 5	Indexing and mapping a genome with Bowtie2
9	Thu Oct 8	Indexing and mapping with STAR
	Mon Oct 12	NO CLASS (Holiday)
10	Thu Oct 15	Calling variants: genotype likelihoods
11	Mon Oct 19	 Analyzing variant data
12	Thu Oct 22	RStudio introduction
13	Mon Oct 26	Wrangling data
14	Thu Oct 29	Reading in and modifying GEO datasets
15	Mon Nov 2	Plotting: basic and ggplot2
16	Thu Nov 5	Generating a heatmap from real data
17	Mon Nov 9	Intro to differential gene expression (DGE) analysis
18	Thu Nov 12	DGE workflow in RStudio; PCA plots
19	Mon Nov 16	Visualizing DGE results: heatmaps, scatterplots
20	Thu Nov 19	Start-to-finish DGE with new data
21	Mon Nov 23	In-class exam
	Thu Nov 26	NO CLASS (Holiday)
22	Mon Nov 30	Analyzing DGE results
23	Thu Dec 3	Pairwise and multiple-sequence alignment
24	Mon Dec 7	Tree-building methods; bootstrapping 
25	Thu Dec 10	Phylogenetic analysis with "ape" package

