 Verticillium_clocks
==========

Documentation of identification of clock genes in verticillium genomes


Note - all this work was performed in the directory:
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks

The following is a summary of the work presented in this Readme.

The following processes were applied to Fusarium genomes prior to analysis:
Data qc
Genome assembly
Repeatmasking
Gene prediction
Functional annotation

Analyses performed on these genomes involved BLAST searching for:


#Building of directory structure

#Data organisation

Data was copied from the raw_data repository to a local directory for assembly
and annotation.

```bash

  # For original sequencing runs
  mkdir -p /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks
	cd /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks
	Species="V.dahliae"
	Strain="51"
	mkdir -p raw_dna/paired/$Species/$Strain/F
	mkdir -p raw_dna/paired/$Species/$Strain/R    
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/51/F/wilt_51_F_appended.fastq raw_dna/paired/$Species/$Strain/F/.
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/51/R/wilt_51_R_appended.fastq raw_dna/paired/$Species/$Strain/R/.
  Strain="53"
	mkdir -p raw_dna/paired/$Species/$Strain/F
	mkdir -p raw_dna/paired/$Species/$Strain/R    
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/53/F/wilt_53_F_appended.fastq raw_dna/paired/$Species/$Strain/F/.
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/53/R/wilt_53_R_appended.fastq raw_dna/paired/$Species/$Strain/R/.
  Strain="58"
	mkdir -p raw_dna/paired/$Species/$Strain/F
	mkdir -p raw_dna/paired/$Species/$Strain/R    
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/58/F/wilt_58_F_appended.fastq raw_dna/paired/$Species/$Strain/F/.
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/58/R/wilt_58_R_appended.fastq raw_dna/paired/$Species/$Strain/R/.
  Strain="61"
	mkdir -p raw_dna/paired/$Species/$Strain/F
	mkdir -p raw_dna/paired/$Species/$Strain/R    
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/61/F/wilt_61_F_appended.fastq raw_dna/paired/$Species/$Strain/F/.
  cp /home/groups/harrisonlab/project_files/verticillium_dahliae/wilt/raw_dna/paired/V.dahliae/61/R/wilt_61_R_appended.fastq raw_dna/paired/$Species/$Strain/R/.
  # For new sequencing run
  RawDat=/home/groups/harrisonlab/raw_data/raw_seq/raw_reads/160412_M04465_0010-AMLCU    
  Species="V.dahliae"
  Strain="12008"
  mkdir -p raw_dna/paired/$Species/$Strain/F
  mkdir -p raw_dna/paired/$Species/$Strain/R
  cp $RawDat/Vd12008_S1_L001_R1_001.fastq.gz raw_dna/paired/$Species/$Strain/F/.
  cp $RawDat/Vd12008_S1_L001_R2_001.fastq.gz raw_dna/paired/$Species/$Strain/R/.
```

To gzip files:

for File in $(ls raw_dna/paired/*/*/*/*.fastq); do
gzip $File > $File.gz
done

This process was repeated for RNAseq data:

```bash

```




#Data qc

programs:
  fastqc
  fastq-mcf
  kmc

Data quality was visualised using fastqc:
```bash
	for RawData in $(ls raw_dna/paired/*/*/*/*.fastq.gz); do
		ProgDir=/home/lopeze/git_repos/tools/seq_tools/dna_qc
		echo $RawData;
		qsub $ProgDir/run_fastqc.sh $RawData
	done
```

Trimming was performed on data to trim adapters from
sequences and remove poor quality data. This was done with fastq-mcf

<!-- Firstly, those strains with more than one run were identified:

```bash
	ls

```

```
	raw_dna/paired/F.oxysporum_fsp_cepae/Fus2
	2
	raw_dna/paired/F.oxysporum_fsp_cepae/HB6
	2
``` -->

Trimming was first performed on all strains that had a single run of data:

```bash
	for StrainPath in $(ls -d raw_dna/paired/*/*); do
		ProgDir=/home/lopeze/git_repos/tools/seq_tools/rna_qc
		IlluminaAdapters=/home/lopeze/git_repos/tools/seq_tools/ncbi_adapters.fa
		ReadsF=$(ls $StrainPath/F/*.fastq*)
		ReadsR=$(ls $StrainPath/R/*.fastq*)
		echo $ReadsF
		echo $ReadsR
		qsub $ProgDir/rna_qc_fastq-mcf.sh $ReadsF $ReadsR $IlluminaAdapters DNA
	done
```
<!--
Trimming was then performed for strains with multiple runs of data

```bash
	ProgDir=/home/armita/git_repos/emr_repos/tools/seq_tools/rna_qc
	IlluminaAdapters=/home/armita/git_repos/emr_repos/tools/seq_tools/ncbi_adapters.fa
	echo "Fus2"
	StrainPath=raw_dna/paired/F.oxysporum_fsp_cepae/Fus2
	ReadsF=$(ls $StrainPath/F/s_6_1_sequence.fastq.gz)
	ReadsR=$(ls $StrainPath/R/s_6_2_sequence.fastq.gz)
	qsub $ProgDir/rna_qc_fastq-mcf.sh $ReadsF $ReadsR $IlluminaAdapters DNA
	StrainPath=raw_dna/paired/F.oxysporum_fsp_cepae/Fus2
	ReadsF=$(ls $StrainPath/F/FUS2_S2_L001_R1_001.fastq.gz)
	ReadsR=$(ls $StrainPath/R/FUS2_S2_L001_R2_001.fastq.gz)
	qsub $ProgDir/rna_qc_fastq-mcf.sh $ReadsF $ReadsR $IlluminaAdapters DNA
	echo "HB6"
	StrainPath=raw_dna/paired/F.oxysporum_fsp_cepae/HB6
	ReadsF=$(ls $StrainPath/F/HB6_S4_L001_R1_001.fastq.gz)
	ReadsR=$(ls $StrainPath/R/HB6_S4_L001_R2_001.fastq.gz)
	qsub $ProgDir/rna_qc_fastq-mcf.sh $ReadsF $ReadsR $IlluminaAdapters DNA
	StrainPath=raw_dna/paired/F.oxysporum_fsp_cepae/HB6
	ReadsF=$(ls $StrainPath/F/HB6_S5_L001_R1_001.fastq.gz)
	ReadsR=$(ls $StrainPath/R/HB6_S5_L001_R2_001.fastq.gz)
	qsub $ProgDir/rna_qc_fastq-mcf.sh $ReadsF $ReadsR $IlluminaAdapters DNA
``` -->


Data quality was visualised once again following trimming:
```bash
	for RawData in $(ls qc_dna/paired/*/*/*/*.fq.gz ); do
		ProgDir=/home/lopeze/git_repos/tools/seq_tools/dna_qc
		echo $RawData;
		qsub $ProgDir/run_fastqc.sh $RawData
	done
```

kmer counting was performed using kmc
This allowed estimation of sequencing depth and total genome size

This was performed for strains with single runs of data
```bash
		for TrimPath in $(ls -d qc_dna/paired/*/*); do
		ProgDir=/home/lopeze/git_repos/tools/seq_tools/dna_qc
		TrimF=$(ls $TrimPath/F/*.fq.gz)
		TrimR=$(ls $TrimPath/R/*.fq.gz)
		echo $TrimF
		echo $TrimR
		qsub $ProgDir/kmc_kmer_counting.sh $TrimF $TrimR
		done
```
<!--
and for strains with muiltiple runs of data:

```bash
	for TrimPath in $(ls -d raw_dna/paired/*/Fus2); do
		ProgDir=/home/armita/git_repos/emr_repos/tools/seq_tools/dna_qc
		TrimF1=$(ls $TrimPath/F/s_6_1_sequence.fastq.gz)
		TrimR1=$(ls $TrimPath/R/s_6_2_sequence.fastq.gz)
		echo $TrimF1
		echo $TrimR1
		TrimF2=$(ls $TrimPath/F/FUS2_S2_L001_R1_001.fastq.gz)
		TrimR2=$(ls $TrimPath/R/FUS2_S2_L001_R2_001.fastq.gz)
		echo $TrimF2
		echo $TrimR2
		qsub $ProgDir/kmc_kmer_counting.sh $TrimF1 $TrimR1 $TrimF2 $TrimR2
	done
	for TrimPath in $(ls -d raw_dna/paired/*/HB6); do
		ProgDir=/home/armita/git_repos/emr_repos/tools/seq_tools/dna_qc
		TrimF1=$(ls $TrimPath/F/HB6_S4_L001_R1_001.fastq.gz)
		TrimR1=$(ls $TrimPath/R/HB6_S4_L001_R2_001.fastq.gz)
		echo $TrimF1
		echo $TrimR1
		TrimF2=$(ls $TrimPath/F/HB6_S5_L001_R1_001.fastq.gz)
		TrimR2=$(ls $TrimPath/R/HB6_S5_L001_R2_001.fastq.gz)
		echo $TrimF2
		echo $TrimR2
		qsub $ProgDir/kmc_kmer_counting.sh $TrimF1 $TrimR1 $TrimF2 $TrimR2
	done
``` -->

mode kmer abundance prior to error correction was reported using the following
commands:

```bash
for File in $(ls qc_dna/kmc/*/*/*_true_kmer_summary.txt); do
basename $File;
tail -n3 $File | head -n1 ;
done
```

Results were as follows. Where notes next to the kmer coverage reports a fail,
the results were initally <5 but manual inspection of the kmer distribution graph
revealed the coverage to be greater, an that the <5 result was a result of poor
thresholding and did not represeent median coverage.

```
51_true_kmer_summary.txt
The mode kmer abundance is:  52
53_true_kmer_summary.txt
The mode kmer abundance is:  37
58_true_kmer_summary.txt
The mode kmer abundance is:  71
61_true_kmer_summary.txt
The mode kmer abundance is:  53
```

#Assembly

Assembly was performed with:
* Spades

## Spades Assembly



```bash
    for StrainPath in $(ls -d qc_dna/paired/*/* ); do
    ProgDir=/home/lopeze/git_repos/tools/seq_tools/assemblers/spades
    Strain=$(echo $StrainPath | rev | cut -f1 -d '/' | rev)
    Organism=$(echo $StrainPath | rev | cut -f2 -d '/' | rev)
    F_Read=$(ls $StrainPath/F/*.fq.gz)
    R_Read=$(ls $StrainPath/R/*.fq.gz)
    OutDir=assembly/spades/$Organism/$Strain
    Jobs=$(qstat | grep 'submit_SPA' | grep 'qw' | wc -l)
    while [ $Jobs -gt 1 ]; do
    sleep 5m
    printf "."
    Jobs=$(qstat | grep 'submit_SPA' | grep 'qw' | wc -l)
    done		
    printf "\n"
    echo $F_Read
    echo $R_Read
    qsub $ProgDir/submit_SPAdes.sh $F_Read $R_Read $OutDir correct 10
    done
```


<!--
Assemblies were submitted for genomes with data from multiple sequencing runs:

```bash
for StrainPath in $(ls -d qc_dna/paired/F.*/HB6); do
  echo $StrainPath
    ProgDir=/home/ransoe/git_repos/tools/seq_tools/assemblers/spades/multiple_libraries
    Strain=$(echo $StrainPath | rev | cut -f1 -d '/' | rev)
    Organism=$(echo $StrainPath | rev | cut -f2 -d '/' | rev)
    echo $Strain
    echo $Organism
    TrimF1_Read=$(ls $StrainPath/F/HB6_S4_L001_R1_001_trim.fq.gz);
    TrimR1_Read=$(ls $StrainPath/R/HB6_S4_L001_R2_001_trim.fq.gz);
    TrimF2_Read=$(ls $StrainPath/F/HB6_S5_L001_R1_001_trim.fq.gz);
    TrimR2_Read=$(ls $StrainPath/R/HB6_S5_L001_R2_001_trim.fq.gz);
    echo $TrimF1_Read
    echo $TrimR1_Read
    echo $TrimF2_Read
    echo $TrimR2_Read
    OutDir=assembly/spades/$Organism/$Strain
    qsub $ProgDir/subSpades_2lib.sh $TrimF1_Read $TrimR1_Read $TrimF2_Read $TrimR2_Read $OutDir correct 10
  done
	for StrainPath in $(ls -d qc_dna/paired/F.*/Fus2); do
	  echo $StrainPath
	    ProgDir=/home/ransoe/git_repos/tools/seq_tools/assemblers/spades/multiple_libraries
	    Strain=$(echo $StrainPath | rev | cut -f1 -d '/' | rev)
	    Organism=$(echo $StrainPath | rev | cut -f2 -d '/' | rev)
	    echo $Strain
	    echo $Organism
	    TrimF1_Read=$(ls $StrainPath/F/s_6_1_sequence_trim.fq.gz);
	    TrimR1_Read=$(ls $StrainPath/R/s_6_2_sequence_trim.fq.gz);
	    TrimF2_Read=$(ls $StrainPath/F/FUS2_S2_L001_R1_001_trim.fq.gz);
	    TrimR2_Read=$(ls $StrainPath/R/FUS2_S2_L001_R2_001_trim.fq.gz);
	    echo $TrimF1_Read
	    echo $TrimR1_Read
	    echo $TrimF2_Read
	    echo $TrimR2_Read
	    OutDir=assembly/spades/$Organism/$Strain
	    qsub $ProgDir/subSpades_2lib_HiMem.sh $TrimF1_Read $TrimR1_Read $TrimF2_Read $TrimR2_Read $OutDir correct 10
	  done
``` -->

Quast --> quality assessment tool for genome assemblies.

```bash
ProgDir=/home/lopeze/git_repos/tools/seq_tools/assemblers/assembly_qc/quast
for Assembly in $(ls assembly/spades/*/*/filtered_contigs/contigs_min_500bp.fasta); do
Strain=$(echo $Assembly | rev | cut -f3 -d '/' | rev)
Organism=$(echo $Assembly | rev | cut -f4 -d '/' | rev)  
OutDir=assembly/spades/$Organism/$Strain/filtered_contigs
qsub $ProgDir/sub_quast.sh $Assembly $OutDir
done
```
51 reults:
Assembly                   contigs_min_500bp  contigs_min_500bp broken      
# contigs                  1482               1557                    
Largest contig             321888             321888                  
Total length               33065465           33064715                
GC (%)                     55.93              55.93                   
N50                        64178              59021                   
N75                        34220              32519                   

53 results:                
Assembly                   contigs_min_500bp  contigs_min_500bp broken         
# contigs                  1387               1479                    
Largest contig             237640             193510                  
Total length               32389379           32388393                
GC (%)                     56.40              56.40                   
N50                        47913              45145                   
N75                        26178              24006                   

58 results:
Assembly                   contigs_min_500bp  contigs_min_500bp broken             
# contigs                  1160               1262                    
Largest contig             294690             294690                  
Total length               32601233           32600213                
GC (%)                     55.87              55.87                   
N50                        79211              68028                   
N75                        41540              37617                   


61 results:
Assembly                   contigs_min_500bp  contigs_min_500bp broken                 
# contigs                  1239               1364               
Largest contig             359375             331650                  
Total length               32897558           32896308                
GC (%)                     55.64              55.64                   
N50                        81559              71457                   
N75                        41700              36159                   



#Repeatmasking

Repeat masking was performed with:
* Repeatmasker
* Repeatmodeler

The best assembly was used to perform Repeatmasking

```bash

for BestAssembly in $(ls assembly/spades/*/*/filtered_contigs/contigs_min_500bp.fasta);
do
ProgDir=/home/lopeze/git_repos/tools/seq_tools/repeat_masking
qsub $ProgDir/rep_modeling.sh $BestAssembly
qsub $ProgDir/transposonPSI.sh $BestAssembly
done
```

Strain 51:
** % bases masked by hardmasked and softmasked: 3.52% (bases masked:1162406 bp)

** % bases masked by transposon psi: 1.96% (bases masked:647979 bp)

Strain 53:
** % bases masked by hardmasked and softmasked: 2.11% (bases masked:684231 bp)

** % bases masked by transposon psi: 0.6% (bases masked:194701 bp)

Strain 58:
** % bases masked by hardmasked and softmasked: 3.7% (bases masked:1206433 bp)

** % bases masked by transposon psi: 2.13% (bases masked:693007 bp)

Strain 61:
** % bases masked by hardmasked and softmasked: 4.96% (bases masked:1631055 bp)

** % bases masked by transposon psi: 3.42cd % (bases masked:1125600 bp)


Up till now we have been using just the repeatmasker/repeatmodeller fasta file when we have used softmasked fasta files. You can merge in transposonPSI masked sites using the following command:

```bash
for File in $(ls repeat_masked/*/*/filtered_contigs_repmask/*_contigs_softmasked.fa); do
OutDir=$(dirname $File)
TPSI=$(ls $OutDir/*_contigs_unmasked.fa.TPSI.allHits.chains.gff3)
OutFile=$(echo $File | sed 's/_contigs_softmasked.fa/_contigs_softmasked_repeatmasker_TPSI_appended.fa/g')
bedtools maskfasta -soft -fi $File -bed $TPSI -fo $OutFile
echo "$OutFile"
echo "Number of masked bases:"
cat $OutFile | grep -v '>' | tr -d '\n' | awk '{print $0, gsub("[a-z]", ".")}' | cut -f2 -d ' '
done
```

#Gene prediction

Gene prediction followed three steps: Pre-gene prediction - Quality of genome assemblies were assessed using Cegma to see how many core eukaryotic genes can be identified. Gene model training - Gene models were trained using assembled RNAseq data as part of the Braker1 pipeline Gene prediction - Gene models were used to predict genes in genomes as part of the the Braker1 pipeline. This used RNAseq data as hints for gene models.

#Pre-gene prediction

Quality of genome assemblies was assessed by looking for the gene space in the assemblies.

```bash
ProgDir=/home/lopeze/git_repos/tools/gene_prediction/cegma
cd /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks
for Genome in $(ls repeat_masked/V.*/*/*/*_contigs_softmasked.fa); do
echo $Genome;
qsub $ProgDir/sub_cegma.sh $Genome dna;
done
```

** 12251 Number of cegma genes present and complete: 94.76% ** Number of cegma genes present and partial: 97.98% #Prots %Completeness - #Total Average %Ortho Complete 235 94.76 - 282 1.20 16.17 Partial 243 97.98 - 298 1.23 18.52

** 12253 Number of cegma genes present and complete: 94.35% ** Number of cegma genes present and partial: 97.98% #Prots %Completeness - #Total Average %Ortho Complete 234 94.35 - 292 1.25 20.94 Partial 243 97.98 - 309 1.27 22.22

** 12158q Number of cegma genes present and complete: 95.16% ** Number of cegma genes present and partial: 97.18% #Prots %Completeness - #Total Average %Ortho Complete 236 95.16 - 276 1.17 11.44 Partial 241 97.18 - 289 1.20 14.52

** 12261 Number of cegma genes present and complete: 95.56% ** Number of cegma genes present and partial: 97.58% #Prots %Completeness - #Total Average %Ortho Complete 237 95.56 - 276 1.16 11.39 Partial 242 97.58 - 287 1.19 13.64

```bash
ProgDir=/home/lopeze/git_repos/tools/gene_prediction/cegma
cd /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks
for Genome in $(ls repeat_masked/V.*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
echo $Genome;
qsub $ProgDir/sub_cegma.sh $Genome dna;
done
```

Outputs were summarised using the commands:

```bash
for File in $(ls gene_pred/cegma/V.*/*/*_dna_cegma.completeness_report); do
Strain=$(echo $File | rev | cut -f2 -d '/' | rev);
Species=$(echo $File | rev | cut -f3 -d '/' | rev);
printf "$Species\t$Strain\n";
cat $File | head -n18 | tail -n+4;printf "\n";
done > gene_pred/cegma/cegma_results_dna_summary.txt
```

#Gene prediction

Copy raw_rna data from verticillium_dahliae/pathogenomics to verticillium_dahliae/clocks This contained the following data: 12008PDA

12008-PDA_S2_L001_R1_001.fastq.gz 12008-PDA_S2_L001_R2_001.fastq.gz 12008-PDA_S2_L001_R1_001.fastq 12008-PDA_S2_L001_R2_001.fastq

12008CD

12008-CD_S1_L001_R1_001.fastq.gz 12008-CD_S1_L001_R2_001.fastq.gz 12008-CD_S1_L001_R1_001.fastq 12008-CD_S1_L001_R2_001.fastq

##Aligning

Insert sizes of the RNA seq library were unknown until a draft alignment could be made. To do this tophat and cufflinks were run, aligning the reads against a single genome. The fragment length and stdev were printed to stdout while cufflinks was running.

```bash
for Assembly in $(ls repeat_masked/*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
Strain=$(echo $Assembly| rev | cut -d '/' -f3 | rev)
Organism=$(echo $Assembly | rev | cut -d '/' -f4 | rev)
echo "$Organism - $Strain"
for RNADir in $(ls -d qc_rna/paired/V.*/12008PDA); do
Timepoint=$(echo $RNADir | rev | cut -f1 -d '/' | rev)
echo "$Timepoint"
FileF=$(ls $RNADir/F/*_trim.fq.gz)
FileR=$(ls $RNADir/R/*_trim.fq.gz)
OutDir=alignment/$Organism/$Strain/$Timepoint
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/tophat_alignment.sh $Assembly $FileF $FileR $OutDir
done
done
```

51 --> 81.7% overall read mapping rate. 73.0% concordant pair alignment rate.
53 --> 76.5% overall read mapping rate. 68.5% concordant pair alignment rate.
58 --> 73.7% overall read mapping rate. 65.7% concordant pair alignment rate.
61 --> 78.8% overall read mapping rate. 70.1% concordant pair alignment rate.


```bash
for Assembly in $(ls repeat_masked/*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
Strain=$(echo $Assembly| rev | cut -d '/' -f3 | rev)
Organism=$(echo $Assembly | rev | cut -d '/' -f4 | rev)
echo "$Organism - $Strain"
for RNADir in $(ls -d qc_rna/paired/V.*/12008CD); do
Timepoint=$(echo $RNADir | rev | cut -f1 -d '/' | rev)
echo "$Timepoint"
FileF=$(ls $RNADir/F/*_trim.fq.gz)
FileR=$(ls $RNADir/R/*_trim.fq.gz)
OutDir=alignment/$Organism/$Strain/$Timepoint
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/tophat_alignment.sh $Assembly $FileF $FileR $OutDir
done
done
```

51 --> 80.4% overall read mapping rate. 70.8% concordant pair alignment rate.
53 --> 77.4% overall read mapping rate. 68.3% concordant pair alignment rate.
58 --> 70.2% overall read mapping rate. 61.2% concordant pair alignment rate.
61 --> 73.2% overall read mapping rate. 63.8% concordant pair alignment rate.

Alignments were concatenated prior to running cufflinks: Cufflinks was run to produce the fragment length and stdev statistics:

if run the commands in a node other than cluster, using the script:

```bash
qlogin -pe smp 8 -l virtual_free=1G
for Assembly in $(ls /home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/repeat_masked/*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
Strain=$(echo $Assembly| rev | cut -d '/' -f3 | rev)
Organism=$(echo $Assembly | rev | cut -d '/' -f4 | rev)
echo "$Organism - $Strain"
for AcceptedHits in $(ls /home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/alignment/$Organism/$Strain/*/accepted_hits.bam); do
Timepoint=$(echo $AcceptedHits | rev | cut -f2 -d '/' | rev)
echo $Timepoint
OutDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/gene_pred/cufflinks/$Organism/$Strain/"$Timepoint"_prelim
ProgDir=/home/fanron/git_repos/tools/seq_tools/RNAseq
# qsub $ProgDir/sub_cufflinks.sh $AcceptedHits $OutDir
cufflinks -o $OutDir/cufflinks -p 8 --max-intron-length 4000 $AcceptedHits 2>&1 | tee $OutDir/cufflinks/cufflinks.log
done
done
```

if run the commands on cluster other than a node:

```bash
# qlogin -pe smp 8 -l virtual_free=1G
  for Assembly in $(ls repeat_masked/*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
  Strain=$(echo $Assembly| rev | cut -d '/' -f3 | rev)
  Organism=$(echo $Assembly | rev | cut -d '/' -f4 | rev)
  echo "$Organism - $Strain"
  for AcceptedHits in $(ls alignment/$Organism/$Strain/*/accepted_hits.bam); do
  Timepoint=$(echo $AcceptedHits | rev | cut -f2 -d '/' | rev)
  echo $Timepoint
  OutDir=gene_pred/cufflinks/$Organism/$Strain/"$Timepoint"_prelim
  ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
  qsub $ProgDir/sub_cufflinks.sh $AcceptedHits $OutDir
  # cufflinks -o $OutDir/cufflinks -p 8 --max-intron-length 4000 $AcceptedHits 2>&1 | tee $OutDir/cufflinks/cufflinks.log
  done
  done
  ```
cat cufflinks.log

PDA
  12251
  [11:41:29] Inspecting reads and determining fragment length distribution.
> Processed 18133 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 11194717.42
>	Raw Map Mass: 11194717.42
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 237.09
>	           Estimated Std Dev: 62.78
[12:00:19] Assembling transcripts and estimating abundances.
> Processed 18270 loci.                        [*************************] 100%

The Estimated Mean: 237.09 allowed calculation of of the mean insert gap to be
-243bp 237-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.

12253
[11:41:37] Inspecting reads and determining fragment length distribution.
> Processed 18220 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 10448663.00
>	Raw Map Mass: 10448663.00
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 232.95
>	           Estimated Std Dev: 59.55
[11:57:49] Assembling transcripts and estimating abundances.
> Processed 18359 loci.                        [*************************] 100%

The Estimated Mean: 232.95 allowed calculation of of the mean insert gap to be
-247bp 233-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.

12158
[11:41:16] Inspecting reads and determining fragment length distribution.
> Processed 19135 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 10106512.62
>	Raw Map Mass: 10106512.62
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 236.26
>	           Estimated Std Dev: 63.98
[11:55:35] Assembling transcripts and estimating abundances.
> Processed 19296 loci.                        [*************************] 100%

The Estimated Mean: 236.26 allowed calculation of of the mean insert gap to be
-244bp 236-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.

12161
[11:47:48] Inspecting reads and determining fragment length distribution.
> Processed 19194 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 10828749.04
>	Raw Map Mass: 10828749.04
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 235.63
>	           Estimated Std Dev: 63.60
[12:04:22] Assembling transcripts and estimating abundances.
> Processed 19343 loci.                        [*************************] 100%

The Estimated Mean: 235.63 allowed calculation of of the mean insert gap to be
-244bp 236-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.

CD
12251
[10:34:30] Inspecting reads and determining fragment length distribution.
> Processed 17030 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 8313367.45
>	Raw Map Mass: 8313367.45
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 225.19
>	           Estimated Std Dev: 63.29
[10:37:11] Assembling transcripts and estimating abundances.
> Processed 17170 loci.                        [*************************] 100%

The Estimated Mean: 225.19 allowed calculation of of the mean insert gap to be
-255bp 225-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.


12253
[10:34:30] Inspecting reads and determining fragment length distribution.
> Processed 17094 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 8000277.15
>	Raw Map Mass: 8000277.15
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 226.85
>	           Estimated Std Dev: 64.80
[10:36:56] Assembling transcripts and estimating abundances.
> Processed 17239 loci.                        [*************************] 100%

The Estimated Mean: 226.85 allowed calculation of of the mean insert gap to be
-253bp 227-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.

12158
[10:27:12] Inspecting reads and determining fragment length distribution.
> Processed 18592 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 7320481.83
>	Raw Map Mass: 7320481.83
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 222.72
>	           Estimated Std Dev: 62.99
[10:29:35] Assembling transcripts and estimating abundances.
> Processed 18761 loci.                        [*************************] 100%

The Estimated Mean: 222.72 allowed calculation of of the mean insert gap to be
-257bp 223-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.

12161
[10:33:29] Inspecting reads and determining fragment length distribution.
> Processed 18620 loci.                        [*************************] 100%
> Map Properties:
>	Normalized Map Mass: 7639017.83
>	Raw Map Mass: 7639017.83
>	Fragment Length Distribution: Empirical (learned)
>	              Estimated Mean: 224.52
>	           Estimated Std Dev: 64.72
[10:36:08] Assembling transcripts and estimating abundances.
> Processed 18786 loci.                        [*************************] 100%

The Estimated Mean: 224.52 allowed calculation of of the mean insert gap to be
-255bp 225-(240*2) where 240? was the mean read length. This was provided to tophat
on a second run (as the -r option) along with the fragment length stdev to
increase the accuracy of mapping.

```

Then Rnaseq data was aligned to each genome assembly:

```bash
for Assembly in $(ls repeat_masked/*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
Strain=$(echo $Assembly| rev | cut -d '/' -f3 | rev)
Organism=$(echo $Assembly | rev | cut -d '/' -f4 | rev)
echo "$Organism - $Strain"
for RNADir in $(ls -d qc_rna/paired/*/12008PDA | grep -v -e '_rep'); do
Timepoint_PDA=$(echo $RNADir | rev | cut -f1 -d '/' | rev)
echo "$Timepoint_PDA"
FileF=$(ls $RNADir/F/*_trim.fq.gz)
FileR=$(ls $RNADir/R/*_trim.fq.gz)
OutDir=alignment/$Organism/$Strain/$Timepoint_PDA
InsertGap='-250'
InsertStdDev='64'
Jobs=$(qstat | grep 'tophat' | grep 'qw' | wc -l)
while [ $Jobs -gt 1 ]; do
sleep 10
printf "."
Jobs=$(qstat | grep 'tophat' | grep 'qw' | wc -l)
done
printf "\n"
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/tophat_alignment.sh $Assembly $FileF $FileR $OutDir $InsertGap $InsertStdDev
done
done
```
cd alignment/repeat_masked/
mkdir 12008PDA_accurate
cp -r 12008PDA/* 12008PDA_accurate/

    51 --> 81.7% overall read mapping rate. 73.0% concordant pair alignment rate.
    53 --> 76.5% overall read mapping rate. 68.5% concordant pair alignment rate.
    58 --> 73.7% overall read mapping rate. 65.7% concordant pair alignment rate.
    61 --> 78.8% overall read mapping rate. 70.1% concordant pair alignment rate.

```bash
for Assembly in $(ls repeat_masked/*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
Strain=$(echo $Assembly| rev | cut -d '/' -f3 | rev)
Organism=$(echo $Assembly | rev | cut -d '/' -f4 | rev)
echo "$Organism - $Strain"
for RNADir in $(ls -d qc_rna/paired/*/12008CD | grep -v -e '_rep'); do
Timepoint_CD=$(echo $RNADir | rev | cut -f1 -d '/' | rev)
echo "$Timepoint_CD"
FileF=$(ls $RNADir/F/*_trim.fq.gz)
FileR=$(ls $RNADir/R/*_trim.fq.gz)
OutDir=alignment/$Organism/$Strain/$Timepoint_CD
InsertGap='-255'
InsertStdDev='64'
Jobs=$(qstat | grep 'tophat' | grep 'qw' | wc -l)
while [ $Jobs -gt 1 ]; do
sleep 10
printf "."
Jobs=$(qstat | grep 'tophat' | grep 'qw' | wc -l)
done
printf "\n"
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/tophat_alignment.sh $Assembly $FileF $FileR $OutDir $InsertGap $InsertStdDev
done
done
  ```
  51 --> 80.4% overall read mapping rate. 70.8% concordant pair alignment rate.
  53 --> 77.4% overall read mapping rate. 68.3% concordant pair alignment rate.
  58 --> 70.2% overall read mapping rate. 61.2% concordant pair alignment rate.
  61 --> 73.2% overall read mapping rate. 63.8% concordant pair alignment rate.


##Braker prediction

Before braker predictiction was performed, I double checked that I had the genemark key in my user area and copied it over from the genemark install directory:

```bash
ls ~/.gm_key
cp /home/armita/prog/genemark/gm_key_64 ~/.gm_key
```

Braker predictiction was performed using softmasked genome, not unmasked one.

```bash
for Assembly in $(ls repeat_masked/*/*/*/*_contigs_softmasked_repeatmasker_TPSI_appended.fa); do
Jobs=$(qstat | grep 'tophat' | grep -w 'r' | wc -l)
while [ $Jobs -gt 1 ]; do
sleep 10
printf "."
Jobs=$(qstat | grep 'tophat' | grep -w 'r' | wc -l)
done
printf "\n"
Strain=$(echo $Assembly| rev | cut -d '/' -f3 | rev)
Organism=$(echo $Assembly | rev | cut -d '/' -f4 | rev)
echo "$Organism - $Strain"
OutDir=gene_pred/braker/$Organism/"$Strain"_braker_sixth
AcceptedHits=alignment/$Organism/$Strain/concatenated/concatenated.bam
mkdir -p alignment/$Organism/$Strain/concatenated
samtools merge -f $AcceptedHits \
alignment/V.dahliae/*/12008CD/accepted_hits.bam \
alignment/V.dahliae/*/12008PDA/accepted_hits.bam
GeneModelName="$Organism"_"$Strain"_braker_sixth
rm -r /home/lopeze/prog/augustus-3.1/config/species/"$Organism"_"$Strain"_braker_sixth
ProgDir=/home/lopeze/git_repos/tools/gene_prediction/braker1
qsub $ProgDir/sub_braker_fungi.sh $Assembly $OutDir $AcceptedHits $GeneModelName
done
  ```
