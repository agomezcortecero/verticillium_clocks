#V. dahliae RNAseq

In order to open and extract the files from the .tar document:
tar -xvf C101HW16120207.tar

##Building a directory structure
RawDatDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNAseq_data/C101HW16120207/raw_data
ProjectDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/raw_RNA/experiment1/V.dahliae/$Strain

To create folders F and R inside each strain folder:

```bash
ls > t
for folder in $(cat t); do
  echo $folder
  mkdir -p ./"$folder"/F
  mkdir -p ./"$folder"/R
done
rm t
```

Sequence data was moved to the correct directory

```bash
RawDatDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNAseq_data/C101HW16120207/raw_data
ProjectDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/raw_rna
    mv $RawDatDir/EC_1_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD18_rep1/F/.
    mv $RawDatDir/EC_1_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD18_rep1/R/.
    mv $RawDatDir/EC_2_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD18_rep2/F/.
    mv $RawDatDir/EC_2_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD18_rep2/R/.
    mv $RawDatDir/EC_3_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD18_rep3/F/.
    mv $RawDatDir/EC_3_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD18_rep3/R/.
    mv $RawDatDir/EC_4_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD18_rep1/F/.
    mv $RawDatDir/EC_4_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD18_rep1/R/.
    mv $RawDatDir/EC_5_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD18_rep2/F/.
    mv $RawDatDir/EC_5_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD18_rep2/R/.
    mv $RawDatDir/EC_6_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD18_rep3/F/.
    mv $RawDatDir/EC_6_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD18_rep3/R/.
    mv $RawDatDir/EC_7_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD24_rep1/F/.
    mv $RawDatDir/EC_7_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD24_rep1/R/.
    mv $RawDatDir/EC_8_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD24_rep2/F/.
    mv $RawDatDir/EC_8_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD24_rep2/R/.
    mv $RawDatDir/EC_9_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD24_rep3/F/.
    mv $RawDatDir/EC_9_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD24_rep3/R/.
    mv $RawDatDir/EC_10_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD24_rep1/F/.
    mv $RawDatDir/EC_10_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD24_rep1/R/.
    mv $RawDatDir/EC_11_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD24_rep2/F/.
    mv $RawDatDir/EC_11_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD24_rep2/R/.
    mv $RawDatDir/EC_12_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD24_rep3/F/.
    mv $RawDatDir/EC_12_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD24_rep3/R/.
    mv $RawDatDir/EC_13_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD6_rep1/F/.
    mv $RawDatDir/EC_13_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD6_rep1/R/.
    mv $RawDatDir/EC_14_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD6_rep2/F/.
    mv $RawDatDir/EC_14_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD6_rep2/R/.
    mv $RawDatDir/EC_15_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD6_rep3/F/.
    mv $RawDatDir/EC_15_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD6_rep3/R/.
    mv $RawDatDir/EC_16_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD6_rep1/F/.
    mv $RawDatDir/EC_16_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD6_rep1/R/.
    mv $RawDatDir/EC_17_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD6_rep2/F/.
    mv $RawDatDir/EC_17_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD6_rep2/R/.
    mv $RawDatDir/EC_18_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD6_rep3/F/.
    mv $RawDatDir/EC_18_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD6_rep3/R/.
    mv $RawDatDir/EC_19_1.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_DD6_rep1/F/.
    mv $RawDatDir/EC_19_2.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_DD6_rep1/R/.
    mv $RawDatDir/EC_20_1.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_DD6_rep2/F/.
    mv $RawDatDir/EC_20_2.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_DD6_rep2/R/.
    mv $RawDatDir/EC_21_1.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_DD6_rep3/F/.
    mv $RawDatDir/EC_21_2.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_DD6_rep3/R/.
    mv $RawDatDir/EC_22_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD12_rep1/F/.
    mv $RawDatDir/EC_22_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD12_rep1/R/.
    mv $RawDatDir/EC_23_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD12_rep2/F/.
    mv $RawDatDir/EC_23_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD12_rep2/R/.
    mv $RawDatDir/EC_24_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD12_rep3/F/.
    mv $RawDatDir/EC_24_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_DD12_rep3/R/.
    mv $RawDatDir/EC_25_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD12_rep1/F/.
    mv $RawDatDir/EC_25_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD12_rep1/R/.
    mv $RawDatDir/EC_26_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD12_rep2/F/.
    mv $RawDatDir/EC_26_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD12_rep2/R/.
    mv $RawDatDir/EC_27_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD12_rep3/F/.
    mv $RawDatDir/EC_27_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_DD12_rep3/R/.
    mv $RawDatDir/EC_28_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_LL6_rep1/F/.
    mv $RawDatDir/EC_28_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_LL6_rep1/R/.
    mv $RawDatDir/EC_29_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_LL6_rep2/F/.
    mv $RawDatDir/EC_29_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_LL6_rep2/R/.
    mv $RawDatDir/EC_30_1.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_LL6_rep3/F/.
    mv $RawDatDir/EC_30_2.fq.gz $ProjectDir/experiment1/V.dahliae/53WT_LL6_rep3/R/.
    mv $RawDatDir/EC_31_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_LL6_rep1/F/.
    mv $RawDatDir/EC_31_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_LL6_rep1/R/.
    mv $RawDatDir/EC_32_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_LL6_rep2/F/.
    mv $RawDatDir/EC_32_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_LL6_rep2/R/.
    mv $RawDatDir/EC_33_1.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_LL6_rep3/F/.
    mv $RawDatDir/EC_33_2.fq.gz $ProjectDir/experiment1/V.dahliae/Frq08_LL6_rep3/R/.
    mv $RawDatDir/EC_34_1.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_LL6_rep1/F/.
    mv $RawDatDir/EC_34_2.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_LL6_rep1/R/.
    mv $RawDatDir/EC_35_1.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_LL6_rep2/F/.
    mv $RawDatDir/EC_35_2.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_LL6_rep2/R/.
    mv $RawDatDir/EC_36_1.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_LL6_rep3/F/.
    mv $RawDatDir/EC_36_2.fq.gz $ProjectDir/experiment1/V.dahliae/Wc153_LL6_rep3/R/.
```

#Data QC
Perform qc of RNAseq timecourse data

```bash
screen -a
for FilePath in $(ls -d raw_rna/experiment1/V.*/*); do
#Strain=$(echo $FilePath | rev | cut -f1 -d '/' | rev)
echo $FilePath
FileF=$(ls $FilePath/F/*.fq.gz);
FileR=$(ls $FilePath/R/*.fq.gz);
IlluminaAdapters=/home/armita/git_repos/emr_repos/tools/seq_tools/ncbi_adapters.fa
ProgDir=/home/armita/git_repos/emr_repos/tools/seq_tools/rna_qc
qsub $ProgDir/rna_qc_fastq-mcf.sh $FileF $FileR $IlluminaAdapters RNA
sleep 10m
done

  ```

Data quality was visualised using fastqc:

```bash
for RawData in $(ls qc_rna/experiment1/V.dahliae/*/*/*.fq.gz); do
        ProgDir=/home/armita/git_repos/emr_repos/tools/seq_tools/dna_qc
        echo $RawData;
        qsub $ProgDir/run_fastqc.sh $RawData
    done
```

##Trim data

Trimming was performed on data to trim adapters from sequences and remove poor quality data. This was done with fastq-mcf

Trimming was first performed on the strain that had a single run of data:

```bash
for StrainPath in $(ls -d raw_rna/experiment1/V.dahliae/*); do
        ProgDir=/home/armita/git_repos/emr_repos/tools/seq_tools/rna_qc
        IlluminaAdapters=/home/armita/git_repos/emr_repos/tools/seq_tools/ncbi_adapters.fa
        ReadsF=$(ls $StrainPath/F/*.fq*)
        ReadsR=$(ls $StrainPath/R/*.fq*)
        echo $ReadsF
        echo $ReadsR
        qsub $ProgDir/rna_qc_fastq-mcf.sh $ReadsF $ReadsR $IlluminaAdapters DNA
        sleep 5m
    done
    ```

    Data quality was visualised once again following trimming:

```bash
      for RawData in $(ls qc_rna/experiment1/V.dahliae/*/*/*.fq.gz); do
        ProgDir=/home/armita/git_repos/emr_repos/tools/seq_tools/dna_qc
        echo $RawData;
        qsub $ProgDir/run_fastqc.sh $RawData
      done
      ```

  ##Filter data

```bash
for Strain in $(ls ./* -d) ; do
echo $Strain
mkdir -p /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/analysis/bowtie/experiment1/V.dahliae/"$Strain"/F/
mkdir -p /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/analysis/bowtie/experiment1/V.dahliae/"$Strain"/R/
done
```

```bash
for FilePath in $(ls -d /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/*); do
Strain=$(echo $FilePath | rev | cut -f1 -d '/' | rev)
echo $Strain
F_Read=$(ls $FilePath/F/*.fq.gz)
R_Read=$(ls $FilePath/R/*.fq.gz)
echo $F_Read
echo $R_read
/home/groups/harrisonlab/project_files/quorn/scripts/bowtie.sh \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/"$Strain"/F \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/"$Strain"/R \
/home/groups/harrisonlab/project_files/quorn/filtered/phix/phix \ /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/analysis/bowtie/experiment1/V.dahliae/"$Strain"/ \ "$Strain" 150 300 \
done
```

The results showed 0 reads 0.00% overall alignment rate which means there's no Phix in the samples.



#Align to reference genome using STAR

The program was copied to:
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks


```bash
for Strain in $(ls ./* -d) ; do
echo $Strain
mkdir -p /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment2/V.dahliae/"$Strain"
mkdir -p /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment2/V.dahliae/"$Strain"
done
```

#Not used

```bash
STAR
for FilePath in $(ls -d /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment2/V.dahliae/*); do
Strain=$(echo $FilePath | rev | cut -f1 -d '/' | rev)
echo $Strain
F_Read=$(ls $FilePath/F/*.fq.gz)
R_Read=$(ls $FilePath/R/*.fq.gz)
echo $F_Read
echo $R_read
qsub sub_star.sh
./STAR \
--runThreadN 16 \
--runMode genomeGenerate \
--genomeDir /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment2/V.dahliae \
--outFileNamePrefix /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment2/V.dahliae/WT08_DD6_rep1 \
--readFilesCommand zcat \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment2/V.dahliae/WT08_DD6_rep1/F/*.fq.gz \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment2/V.dahliae/WT08_DD6_rep1/R/*.fq.gz \
--outSAMtype SAM
done
```



 ##To create the index file for STAR:

Remove the spaces from the Chromosomes names and subtitute them with _

```cat Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel.fa | cut -f1 -d ' ' > Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel_parsed.fa
 cat Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel.fa |sed 's/ /_/g' > Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel_parsed.fa
```

#-----
#First attempt
#-----

JR2 Genome


```
./STAR \
--runMode genomeGene rate \
--genomeDir /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment1/V.dahliae \
--genomeFastaFiles /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel_parsed.fa \
--sjdbGTFtagExonParentTranscript Parent \
--sjdbGTFfile /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33_parsed.gff3 \
--outFileNamePrefix /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment1/V.dahliae/53WT_DD12_rep1/ \ --readFilesCommand zcat \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/53WT_DD12_rep1/F/*.fq.gz \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/53WT_DD12_rep1/R/*.fq.gz \
--outSAMtype SAM \
--runThreadN 16
```

12008 Genome

```
./STAR \
--runMode genomeGenerate \
--genomeDir /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment1/V.dahliae \
--genomeFastaFiles /home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/repeat_masked/V.dahliae/12008/ncbi_filtered_contigs_repmask/12008_contigs_unmasked.fa \
--sjdbGTFtagExonParentTranscript ID \
--sjdbGTFfile /home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/gene_pred/final_genes/V.dahliae/12008/final/final_genes_appended.gff3 \
--outFileNamePrefix /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment1/V.dahliae/53WT_DD12_rep1/ \
--readFilesCommand zcat \
--readFilesIn /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/53WT_DD12_rep1/F/*.fq.gz \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/53WT_DD12_rep1/R/*.fq.gz \
--outSAMtype SAM \
--runThreadN 16
```



#------
# 2nd attempt
#------

12008

### To create the Index File

#GenomeDir=$WorkDir/index
#InGenome=../pathogenomics/repeat_masked/V.dahliae/12008/ncbi_filtered_contigs_repmask/12008_contigs_unmasked.fa
#InGff=/home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/gene_pred/final_genes/V.dahliae/12008/final/final_genes_appended.gff3
# ParentFeature="ID"

./STAR \
--runMode genomeGenerate \
--genomeDir $GenomeDir \
--genomeFastaFiles $InGenome \
--sjdbGTFtagExonParentTranscript $ParentFeature \
--sjdbGTFfile $InGff
--runThreadN 16 \
--sjdbOverhang ReadLength-1

### To align reads with STAR
./STAR \
--genomeDir $GenomeDir
--outFileNamePrefix /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/STAR/experiment1/V.dahliae/53WT_DD12_rep1/ \
--readFilesCommand zcat \
--readFilesIn /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/53WT_DD12_rep1/F/*.fq.gz \
/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/qc_rna/experiment1/V.dahliae/53WT_DD12_rep1/R/*.fq.gz \
--outSAMtype SAM \
--runThreadN 16


JR2

### To create the Index File

GenomeDir=RNA_alignment/STAR/experiment1/V.dahliae/53WT_DD12_rep1
InGenome=public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel.fa
InGff=public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33_parsed.gff3
ParentFeature="Parent"

./STAR \
--runMode genomeGenerate \
--genomeDir $GenomeDir \
--genomeFastaFiles $InGenome \
--sjdbGTFtagExonParentTranscript $ParentFeature \
--sjdbGTFfile $InGff
--runThreadN 16 \
--sjdbOverhang ReadLength-1


### To align reads with STAR

screen -a
qlogin -pe smp 16 -l virtual_free=1.1G

GenomeDir=RNA_alignment/STAR/experiment1/V.dahliae/53WT_DD12_rep3
OutDir=RNA_alignment/STAR/experiment1/V.dahliae/53WT_DD12_rep3/53WT_DD12_rep3
InReadF=qc_rna/experiment1/V.dahliae/53WT_DD12_rep3/F/*.fq.gz
InReadR=qc_rna/experiment1/V.dahliae/53WT_DD12_rep3/R/*.fq.gz

./STAR \
--genomeDir $GenomeDir \
--outFileNamePrefix $OutDir \
--readFilesCommand zcat \
--readFilesIn $InReadF $InReadR \
--outSAMtype SAM \
--runThreadN 16


#!/bin/bash
#Align RNAseq data with genome using STAR

#$ -S /bin/bash
#$ -cwd
#$ -pe smp 8
#$ -l virtual_free=1.2G

# ---------------
# Step 1
# Collect inputs
# ---------------
echo "Hello"
InGenome=$(basename $1)
InGff=$(basename $2)
InReadF=$(basename $3)
InReadR=$(basename $4)
# genomeDir=$(basname $5)
OutDir=$5

CurDir=$PWD
WorkDir=$TMPDIR/star
genomeDir=$WorkDir/index
echo "$WorkDir"
echo "$genomeDir"
mkdir -p $genomeDir
ls $genomeDir
cd $WorkDir

cp $CurDir/$1 $InGenome
cp $CurDir/$2 $In
cp $CurDir/$3 $InReadF
cp $CurDir/$4 $InReadR
# cp $CurDir/$5 $GenomeDir
cp $CurDir/$5 $OutDir



# ---------------
# Step 2
# Create the Index File
# ---------------
echo "Building index file"
ParentFeature="Parent"
# ParentFeature="ID"

/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/STAR \
--runMode genomeGenerate \
--genomeDir $genomeDir \
--genomeFastaFiles $InGenome \
--sjdbGTFtagExonParentTranscript $ParentFeature \
--sjdbGTFfile $InGff \
--runThreadN 8 \
--sjdbOverhang 99

# ---------------
# Step 2=3
# Run STAR
# ---------------

echo "Aligning RNAseq reads"

/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/STAR \
--genomeDir $genomeDir \
--outFileNamePrefix star_aligment \
--readFilesCommand zcat \
--readFilesIn $InReadF $InReadR \
--outSAMtype SAM \
--runThreadN 8


rm -r $genomeDir
rm $InGenome
rm $InGff
rm $InReadF
rm $InReadR
mkdir -p $CurDir/$OutDir
cp -r $WorkDir $CurDir/$OutDir/.



## Run sub_star.sh in data set

```bash
InGenome=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel.fa)
InGff=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33.gff3)
InReadF=$(ls qc_rna/experiment2/V.dahliae/WT08_DD18_rep1/F/*.fq.gz)
InReadR=$(ls qc_rna/experiment2/V.dahliae/WT08_DD18_rep1/R/*.fq.gz)
OutDir=RNA_alignment/STAR/experiment2/V.dahliae/WT08_DD18_rep1/
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/sub_star.sh $InGenome $InGff $InReadF $InReadR $OutDir
```

## Run sub_star.sh in a loop
q
```bash
for FilePath in $(ls -d qc_rna/experiment2/V.dahliae/*); do
Strain=$(echo $FilePath | rev | cut -f1 -d '/' | rev)
InGenome=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel.fa)
InGff=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33.gff3)
InReadF=$(ls qc_rna/experiment2/V.dahliae/$Strain/F/*.fq.gz)
InReadR=$(ls qc_rna/experiment2/V.dahliae/$Strain/R/*.fq.gz)
OutDir=RNA_alignment/STAR/experiment2/V.dahliae/$Strain/
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/sub_star.sh $InGenome $InGff $InReadF $InReadR $OutDir
done
```


#FeatureCounts

Is a highly efficient general-purpose read summarization program that counts mapped reads for genomic features such as genes, exons, promoter, gene bodies, genomic bins and chromosomal locations. It can be used to count both RNA-seq and genomic DNA-seq reads.



```bash
for Strain in $(ls ./* -d) ; do
echo $Strain
mkdir -p /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/featureCounts/experiment2/V.dahliae/"$Strain"
mkdir -p /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/featureCounts/experiment2/V.dahliae/"$Strain"
done
```


```bash
InBam=$(ls RNA_alignment/STAR/experiment1/V.dahliae/Wc153_LL6_rep3/star/*.sam)
InGff=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33.gff3)
#InGenome=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel.fa)
OutDir=RNA_alignment/featureCounts/experiment1/V.dahliae/Wc153_LL6_rep3/featureCounts/Wc153_LL6_rep3_gene_featurecounts.txt
./subread-1.5.1-source/bin/featureCounts -p -B -M -R -a $InGff -t gene -g "gene_id" -o $OutDir $InBam

```

Status  RNA_alignment/STAR/experiment1/V.dahliae/53WT_DD12_rep1/star/star_aligmentAligned.out.sam
Assigned        34203674
Unassigned_Ambiguity    10911560
Unassigned_MultiMapping 0
Unassigned_NoFeatures   1353797
Unassigned_Unmapped     35332
Unassigned_MappingQuality       0
Unassigned_FragmentLength       0
Unassigned_Chimera      0
Unassigned_Secondary    0
Unassigned_Nonjunction  0
Unassigned_Duplicate    0


Write .sh file for featureCounts program:

```bash
#!/bin/bash
#Align RNAseq data with genome using featureCounts

#$ -S /bin/bash
#$ -cwd
#$ -pe smp 4
#$ -l virtual_free=1.2G

# ---------------
# Step 1
# Collect inputs
# ---------------

InBam=$(basename $1)
InGff=$(basename $2)
OutDir=$3
Prefix=$4

CurDir=$PWD
WorkDir=$TMPDIR/featureCounts
echo "$WorkDir"
mkdir -p $WorkDir
cd $WorkDir

cp $CurDir/$1 $InBam
cp $CurDir/$2 $InGff
cp $CurDir/$3 $OutDir


# ---------------
# Step 2
# Run featureCounts
# ---------------

/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/subread-1.5.1-source/bin/featureCounts \
-p -B -M -R -a $InGff -t gene -g "gene_id" -o "$Prefix"_gene_featurecounts.txt $InBam


rm $InBam
rm $InGff
mkdir -p $CurDir/$OutDir
cp -r $WorkDir $CurDir/$OutDir/.
```

## Run sub_featureCounts.sh in data set

```bash
InBam=$(ls RNA_alignment/STAR/experiment2/V.dahliae/WT08_DD12_rep1/star/*.sam)
InGff=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33.gff3)
OutDir=RNA_alignment/featureCounts/experiment2/V.dahliae/WT08_DD12_rep1/
Prefix=53WT_DD12_rep1
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/sub_featureCounts.sh $InBam $InGff $OutDir $Prefix
```

## Run sub_featureCounts.sh in a loop

```bash
for FilePath in $(ls -d qc_rna/experiment2/V.dahliae/*); do
Strain=$(echo $FilePath | rev | cut -f1 -d '/' | rev)
InBam=$(ls RNA_alignment/STAR/experiment2/V.dahliae/$Strain/star/*.sam)
InGff=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33.gff3)
OutDir=RNA_alignment/featureCounts/experiment1/V.dahliae/$Strain/
Prefix=$Strain
ProgDir=/home/lopeze/git_repos/tools/seq_tools/RNAseq
qsub $ProgDir/sub_featureCounts.sh $InBam $InGff $OutDir $Prefix
done
```



#Import data from featureCounts into R

Create a file with different columns about the experiment treatments:

Sample  Strain  Time    Light
53WT_LL6_rep1   53WT    6h      l
53WT_LL6_rep2   53WT    6h      l
53WT_LL6_rep3   53WT    6h      l
Frq08_LL6_rep1  Frq08   6h      l
Frq08_LL6_rep2  Frq08   6h      l
Frq08_LL6_rep3  Frq08   6h      l
Wc153_LL6_rep1  Wc153   6h      l
Wc153_LL6_rep2  Wc153   6h      l
Wc153_LL6_rep3  Wc153   6h      l
53WT_DD6_rep1   53WT    6h      d
53WT_DD6_rep2   53WT    6h      d
53WT_DD6_rep3   53WT    6h      d
Frq08_DD6_rep1  Frq08   6h      d
Frq08_DD6_rep2  Frq08   6h      d
Frq08_DD6_rep3  Frq08   6h      d
Wc153_DD6_rep1  Wc153   6h      d
Wc153_DD6_rep2  Wc153   6h      d
Wc153_DD6_rep3  Wc153   6h      d
53WT_DD12_rep1  53WT    12h     d
53WT_DD12_rep2  53WT    12h     d
53WT_DD12_rep3  53WT    12h     d
Frq08_DD12_rep1 Frq08   12h     d
Frq08_DD12_rep2 Frq08   12h     d
Frq08_DD12_rep3 Frq08   12h     d
53WT_DD18_rep1  53WT    DD18h   d
53WT_DD18_rep2  53WT    DD18h   d
53WT_DD18_rep3  53WT    DD18h   d
Frq08_DD18_rep1 Frq08   DD18h   d
Frq08_DD18_rep2 Frq08   DD18h   d
Frq08_DD18_rep3 Frq08   DD18h   d
53WT_DD24_rep1  53WT    24h     d
53WT_DD24_rep2  53WT    24h     d
53WT_DD24_rep3  53WT    24h     d
Frq08_DD24_rep1 Frq08   24h     d
Frq08_DD24_rep2 Frq08   24h     d
Frq08_DD24_rep3 Frq08   24h     d

# Edit header lines of feature coutn files to ensure they have the treament name rather than file name
```bash


 for File in $(/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/featureCounts/experiment2/V.dahliae/*/featureCounts/*_featurecounts.txt); do
   echo $File;
  Strain=$(echo $File | rev | cut -f1 -d '/' | rev)
  OutDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/featureCounts/experiment2/V.dahliae/$Strain/
   cp $File $OutDir/.;
 done
 for File in $(ls /home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/featureCounts/experiment2/V.dahliae/*/featureCounts/*_featurecounts.txt); do
   Prefix=$(echo $File | rev | cut -f1 -d '/' | rev | sed 's/_featurecounts.txt//g' | sed "s/_totRNA_S.*_L/_L/g")
   sed -ie "s/star_aligmentAligned.sortedByCoord.out.bam/$Prefix/g" $File
done
```

R script to import and merge data into a format good for DESeq2

install.packages("Biostrings", Sys.getenv("R_LIBS_USER"), repos = "http://cran.case.edu" )


```R
#install and load libraries
require("pheatmap")             
require("data.table")

#load tables into a "list of lists"
qq <- lapply(list.files(".",".*_gene_featurecounts.txt$",full.names=T,recursive=T),function(x) fread(x))

#rename the samples column
lapply(qq,function(x) {names(x)[7]<-sub(".*\\/","",sub("\\/star.*","",names(x)[7]))})

#mm <- qq%>%Reduce(function(dtf1,dtf2) inner_join(dtf1,dtf2,by=c("Geneid","Chr","Start","End","Strand","Length")), .)

#merge the "list of lists" into a single table
m <- Reduce(function(...) merge(..., all = T,by=c("Geneid","Chr","Start","End","Strand","Length")), qq)

#convert data.table to data.frame for use with DESeq2
countData <- data.frame(m[,c(1,7:(ncol(m))),with=F])
rownames(countData) <- countData[,1]
countData <- countData[,-1]

#output countData
write.table(countData,"countData_all",sep="\t",na="",quote=F)
#output gene details
write.table(m[,1:6,with=F],"genes_all.txt",sep="\t",quote=F,row.names=F)
```

colnames(countData) <- sub("X","",colnames(countData))
countData <- countData[,colData$Sample]

===========================
#To run DESeq2
===========================
```R
require(DESeq2)

colData <- read.table("colData_all",header=T,sep="\t")

#countData <- read.table("countData2",header=T,sep="\t")
countData <- read.table("countData_all",header=T,sep="\t")

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)

design <- ~Group

dds <- 	DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds <- DESeq(dds, fitType="local", parallel=T)


#Run DESeq2 removing an outlier

library(DESeq2)
colData <- read.table("colData",header=T,sep="\t")
countData <- read.table("countData2",header=T,sep="\t")

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)

#Eliminate Frq08_DD24_rep3 sample from colData and countData
colData <- colData[!(colData$Sample=="Frq08_DD24_rep3"),]      
countData <- subset(countData, select=-Frq08_DD24_rep3)

design <- ~Group
dds <-  DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds <- DESeq(dds, fitType="local")


=================
Sample distanes
=================

vst<-varianceStabilizingTransformation(dds)
sampleDists<-dist(t(assay(vst)))
library("RColorBrewer")
sampleDistMatrix <- as.matrix(sampleDists)
rownames(sampleDistMatrix) <- paste(vst$Group)
colnames(sampleDistMatrix) <- paste(vst$Group)
colors <- colorRampPalette( rev(brewer.pal(9, "Blues")) )(255)
heatmap(sampleDistMatrix)

Sample distances measured with rlog transformation:

rld <- rlog( dds )
sampleDists <- dist( t( assay(rld) ) )
library("RColorBrewer")
sampleDistMatrix <- as.matrix( sampleDists )
rownames(sampleDistMatrix) <- paste(rld$Group)
colnames(sampleDistMatrix) <- paste(rld$Group)
colours = colorRampPalette( rev(brewer.pal(9, "Blues")) )(255)
heatmap( sampleDistMatrix, trace="none", col=colours)

dev.off()

=================
PCA plots
=================

vst<-varianceStabilizingTransformation(dds)
plotPCA(vst,intgroup="Group")

Plot using rlog transformation:
plotPCA(rld,intgroup="Group")
plotPCA(rld,intgroup=c("Time","Group"))


#Plot using rlog transformation, showing sample names:
plotPCA(rld, intgroup="Group")

library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Group", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Group)) +
 geom_point(size=3) +
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) + geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()

ggsave("PCA_sample_names.pdf", pca_plot, dpi=300, height=15, width=20)

===============
Analysis of gene expression
===============

#Example:
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08l6h","Frq08d6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]
# No threshold
sig.res.upregulated2 <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated2 <- sig.res[sig.res$log2FoldChange <0, ]


##53WT L vs D
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTl6h","53WTd6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

summary(res)
write.table(sig.res.upregulated,"WtLDtxt_up",sep="\t",quote=F)
write.table(sig.res.downregulated,"WtLDtxt_down",sep="\t",quote=F)
write.table(sig.res.,"WtLDtxt",sep="\t",quote=F)

out of 3569 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 1799, 50%
LFC < 0 (down)   : 1770, 50%
outliers [1]     : 0, 0%
low counts [2]   : 0, 0%
(mean count < 8)


##Frq08 L vs D
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08bl06h","Frq08d06h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08LD_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08LD_down.txt",sep="\t",quote=F)

write.table(sig.res,"Frq08LD.txt",sep="\t",quote=F)

out of 3299 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 1675, 51%
LFC < 0 (down)   : 1624, 49%
outliers [1]     : 0, 0%
low counts [2]   : 0, 0%
(mean count < 1)


##Wc153 L vs D
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Wc153l6h","Wc153d6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"WC153LD_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"WC153LD_down.txt",sep="\t",quote=F)

write.table(res,"WC153LD.txt",sep="\t",quote=F)

out of 3512 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 1756, 50%
LFC < 0 (down)   : 1756, 50%
outliers [1]     : 0, 0%
low counts [2]   : 0, 0%
(mean count < 4)


##Light 53WT vs Wc153
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTl6h","Wc153l6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"LightWt53Wc153_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"LightWt53Wc153_down.text",sep="\t",quote=F)

write.table(res,"LightWt53Wc153.txt",sep="\t",quote=F)

out of 4793 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 2391, 50%
LFC < 0 (down)   : 2402, 50%
outliers [1]     : 0, 0%
low counts [2]   : 0, 0%
(mean count < 0)


##Dark 53WT vs Wc153
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd6h","Wc153d6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"DarkWt53Wc153_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"DarkWt53Wc153_down.txt",sep="\t",quote=F)

write.table(res,"DarkWt53Wc153.txt",sep="\t",quote=F)

out of 4004 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 2026, 51%
LFC < 0 (down)   : 1978, 49%
outliers [1]     : 0, 0%
low counts [2]   : 0, 0%
(mean count < 0)


##53Wt 6h vs 12h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd6h","53WTd12h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Wt53h6h12_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53h6h12_down.txt",sep="\t",quote=F)

write.table(res,"Wt53h6h12.txt",sep="\t",quote=F)

out of 138 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 102, 74%
LFC < 0 (down)   : 36, 26%
outliers [1]     : 0, 0%
low counts [2]   : 0, 0%
(mean count < 195)

##53Wt 12h vs 18
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd12h","53WTdDD18h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Wt53h12h18_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53h12h18_down.txt",sep="\t",quote=F)

write.table(res,"Wt53h12h18.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 306, 2.7%
LFC < 0 (down)   : 425, 3.7%
outliers [1]     : 3, 0.026%
low counts [2]   : 884, 7.7%
(mean count < 13)

##53Wt 18h vs 24h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTdDD18h","53WTd24h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Wt53h18h24_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53h18h24_down.txt",sep="\t",quote=F)

write.table(res,"Wt53h18h24.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 2, 0.018%
LFC < 0 (down)   : 12, 0.11%
outliers [1]     : 3, 0.026%
low counts [2]   : 0, 0%
(mean count < 0)

##Frq08 6h vs 12h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08d6h","Frq08d12h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08h6h12_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08h6h12_down.txt",sep="\t",quote=F)

write.table(res,"Frq08h6h12.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 288, 2.5%
LFC < 0 (down)   : 142, 1.2%
outliers [1]     : 3, 0.026%
low counts [2]   : 2431, 21%
(mean count < 96)

##Frq08 12h vs 18h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08d12h","Frq08dDD18h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08h12h18_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08h12h18_down.txt",sep="\t",quote=F)

write.table(res,"Frq08h12h18.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 71, 0.62%
LFC < 0 (down)   : 98, 0.86%
outliers [1]     : 3, 0.026%
low counts [2]   : 2873, 25%
(mean count < 141)

##Frq08 18h vs 24h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08dDD18h","Frq08d24h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08h18h24_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08h18h24_down.txt",sep="\t",quote=F)
write.table(res,"Frq08h18h24.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 20, 0.18%
LFC < 0 (down)   : 9, 0.079%
outliers [1]     : 3, 0.026%
low counts [2]   : 1325, 12%
(mean count < 26)

##53Wt 12h vs 24h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd12h","53WTd24h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Wt53h12h24_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53h12h24_down.txt",sep="\t",quote=F)
write.table(res,"Wt53h12h24.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 0, 0%
LFC < 0 (down)   : 5, 0.044%
outliers [1]     : 3, 0.026%
low counts [2]   : 0, 0%
(mean count < 0)

##Fr08 12h vs 24h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08d12h","Frq08d24h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08h12h24_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08h12h24_down.txt",sep="\t",quote=F)
write.table(res,"Frq08h12h24.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 30, 0.26%
LFC < 0 (down)   : 8, 0.07%
outliers [1]     : 3, 0.026%
low counts [2]   : 0, 0%
(mean count < 0)

##53Wt 6h vs 18h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd6h","53WTdDD18h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Wt53h6h18_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53h6h18_down.txt",sep="\t",quote=F)
write.table(res,"Wt53h6h18.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 59, 0.52%
LFC < 0 (down)   : 47, 0.41%
outliers [1]     : 3, 0.026%
low counts [2]   : 884, 7.7%
(mean count < 13)

##Fr08 6h vs 18h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08d6h","Frq08dDD18h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08h6h18_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08h6h18_down.txt",sep="\t",quote=F)
write.table(res,"Frq08h6h18.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 2, 0.018%
LFC < 0 (down)   : 2, 0.018%
outliers [1]     : 3, 0.026%
low counts [2]   : 0, 0%
(mean count < 0)

##Fr08 6hL vs 53WT 6hL
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08l6h","53WTl6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08h6lWT53h6l_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08h6lWT53h6l_down.txt",sep="\t",quote=F)
write.table(res,"Frq08h6lWT53h6l.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 2198, 19%
LFC < 0 (down)   : 1987, 17%
outliers [1]     : 3, 0.026%
low counts [2]   : 0, 0%
(mean count < 0)

##Fr08 6hD vs 53WT 6hD
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08d6h","53WTd6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >=1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <=-1, ]

write.table(sig.res.upregulated,"Frq08h6dWT53h6d_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08h6dWT53h6d_down.txt",sep="\t",quote=F)
write.table(res,"Frq08h6dWT53h6d.txt",sep="\t",quote=F)

out of 11409 with nonzero total read count
adjusted p-value < 0.05
LFC > 0 (up)     : 2569, 23%
LFC < 0 (down)   : 2498, 22%
outliers [1]     : 3, 0.026%
low counts [2]   : 0, 0%
(mean count < 0)


==================
Gene clustering
==================

rld <- rlog( dds )
head( assay(rld) )

library("RColorBrewer")
library("gplots")
library( "genefilter" )

topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 50)
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row", par(lend = 1),
trace="none", dendrogram="column", margins = c(5, 10), col = my_palette, cexCol=0.8,cexRow=0.8

#Gene clustering of different group of samples
library(DESeq2)
colData <- read.table("colData",header=T,sep="\t")
countData <- read.table("countData2",header=T,sep="\t")

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)
#Eliminate Frq08_DD24_rep3 sample from colData and countData
colData <- colData[!(colData$Sample=="Frq08_DD24_rep1"),]      
countData <- subset(countData, select=-Frq08_DD24_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD24_rep2"),]      
countData <- subset(countData, select=-Frq08_DD24_rep2)
colData <- colData[!(colData$Sample=="Frq08_DD24_rep3"),]      
countData <- subset(countData, select=-Frq08_DD24_rep3)
colData <- colData[!(colData$Sample=="Frq08_DD18_rep1"),]      
countData <- subset(countData, select=-Frq08_DD18_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD18_rep2"),]      
countData <- subset(countData, select=-Frq08_DD18_rep2)
colData <- colData[!(colData$Sample=="Frq08_DD18_rep3"),]      
countData <- subset(countData, select=-Frq08_DD18_rep3)
colData <- colData[!(colData$Sample=="Frq08_DD12_rep1"),]      
countData <- subset(countData, select=-Frq08_DD12_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD12_rep2"),]      
countData <- subset(countData, select=-Frq08_DD12_rep2)
colData <- colData[!(colData$Sample=="Frq08_DD12_rep3"),]      
countData <- subset(countData, select=-Frq08_DD12_rep3)
colData <- colData[!(colData$Sample=="Frq08_DD6_rep1"),]      
countData <- subset(countData, select=-Frq08_DD6_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD6_rep2"),]      
countData <- subset(countData, select=-Frq08_DD6_rep2)
colData <- colData[!(colData$Sample=="Frq08_DD6_rep3"),]      
countData <- subset(countData, select=-Frq08_DD6_rep3)
colData <- colData[!(colData$Sample=="Frq08_LL6_rep1"),]      
countData <- subset(countData, select=-Frq08_LL6_rep1)
colData <- colData[!(colData$Sample=="Frq08_LL6_rep2"),]      
countData <- subset(countData, select=-Frq08_LL6_rep2)
colData <- colData[!(colData$Sample=="Frq08_LL6_rep3"),]      
countData <- subset(countData, select=-Frq08_LL6_rep3)



colData <- colData[!(colData$Sample=="Wc153_DD6_rep1"),]      
countData <- subset(countData, select=-Wc153_DD6_rep1)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep2"),]      
countData <- subset(countData, select=-Wc153_DD6_rep2)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep3"),]      
countData <- subset(countData, select=-Wc153_DD6_rep3)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep1"),]      
countData <- subset(countData, select=-Wc153_LL6_rep1)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep2"),]      
countData <- subset(countData, select=-Wc153_LL6_rep2)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep3"),]      
countData <- subset(countData, select=-Wc153_LL6_rep3)

design <- ~Group
dds <-  DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds <- DESeq(dds, fitType="local")

rld <- rlog( dds )
head( assay(rld) )

library("RColorBrewer")
library("gplots")
library( "genefilter" )

topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row", par(lend = 1),
trace="none", dendrogram="column", margins = c(3, 8), col = my_palette, cexCol=0.4,cexRow=0.4


topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="column", margins = c(3, 8), col = my_palette, cexCol=0.4,cexRow=0.4

===============
Plotting results  
===============

##Light 53WT vs Wc153

res= results(dds, alpha=alpha,contrast=c("Group","53WTl6h","Wc153l6h"))
res= results(dds, alpha=alpha,contrast=c("Group","Frq08l6h","53WTl6h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

topGene <- rownames(res)[which.min(res$padj)]
plotCounts(dds, gene="VDAG_JR2_Chr7g03830", intgroup=c("Strain"))


```


#Create a new colData and countData: mix experiments

#Experiment 08
```R
#Gene clustering of different group of samples
library(DESeq2)
colData <- read.table("colData_all",header=T,sep="\t")
countData <- read.table("countData_all",header=T,sep="\t")

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)

#Eliminate sample from colData and countData

colData <- colData[!(colData$Sample=="Frq08_DD24_rep3"),]      
countData <- subset(countData, select=-Frq08_DD24_rep3)

colData <- colData[!(colData$Sample=="Frq53_DD6_rep1"),]      
countData <- subset(countData, select=-Frq53_DD6_rep1)
colData <- colData[!(colData$Sample=="Frq53_DD6_rep2"),]      
countData <- subset(countData, select=-Frq53_DD6_rep2)
colData <- colData[!(colData$Sample=="Frq53_DD6_rep3"),]      
countData <- subset(countData, select=-Frq53_DD6_rep3)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep1"),]      
countData <- subset(countData, select=-Frq53_LL6_rep1)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep2"),]      
countData <- subset(countData, select=-Frq53_LL6_rep2)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep3"),]      
countData <- subset(countData, select=-Frq53_LL6_rep3)

colData <- colData[!(colData$Sample=="WT53_DD24_rep1"),]      
countData <- subset(countData, select=-WT53_DD24_rep1)
colData <- colData[!(colData$Sample=="WT53_DD24_rep2"),]      
countData <- subset(countData, select=-WT53_DD24_rep2)
colData <- colData[!(colData$Sample=="WT53_DD24_rep3"),]      
countData <- subset(countData, select=-WT53_DD24_rep3)
colData <- colData[!(colData$Sample=="WT53_DD18_rep1"),]      
countData <- subset(countData, select=-WT53_DD18_rep1)
colData <- colData[!(colData$Sample=="WT53_DD18_rep2"),]      
countData <- subset(countData, select=-WT53_DD18_rep2)
colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)
colData <- colData[!(colData$Sample=="WT53_DD12_rep1"),]   
countData <- subset(countData, select=-WT53_DD12_rep1)
colData <- colData[!(colData$Sample=="WT53_DD12_rep2"),]      
countData <- subset(countData, select=-WT53_DD12_rep2)
colData <- colData[!(colData$Sample=="WT53_DD12_rep3"),]      
countData <- subset(countData, select=-WT53_DD12_rep3)
colData <- colData[!(colData$Sample=="WT53_DD6_rep1"),]      
countData <- subset(countData, select=-WT53_DD6_rep1)
colData <- colData[!(colData$Sample=="WT53_DD6_rep2"),]      
countData <- subset(countData, select=-WT53_DD6_rep2)
colData <- colData[!(colData$Sample=="WT53_DD6_rep3"),]      
countData <- subset(countData, select=-WT53_DD6_rep3)
colData <- colData[!(colData$Sample=="WT53_LL6_rep1"),]      
countData <- subset(countData, select=-WT53_LL6_rep1)
colData <- colData[!(colData$Sample=="WT53_LL6_rep2"),]      
countData <- subset(countData, select=-WT53_LL6_rep2)
colData <- colData[!(colData$Sample=="WT53_LL6_rep3"),]      
countData <- subset(countData, select=-WT53_LL6_rep3)

colData <- colData[!(colData$Sample=="Wc153_DD6_rep1"),]      
countData <- subset(countData, select=-Wc153_DD6_rep1)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep2"),]      
countData <- subset(countData, select=-Wc153_DD6_rep2)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep3"),]      
countData <- subset(countData, select=-Wc153_DD6_rep3)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep1"),]      
countData <- subset(countData, select=-Wc153_LL6_rep1)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep2"),]      
countData <- subset(countData, select=-Wc153_LL6_rep2)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep3"),]      
countData <- subset(countData, select=-Wc153_LL6_rep3)

write.table(countData,"countData_08",sep="\t",na="",quote=F)
write.table(colData,"colData_08",sep="\t",na="",quote=F)

#Experiment 53_all
#Eliminate sample from colData and countData

colData <- colData[!(colData$Sample=="Frq08_DD24_rep3"),]      
countData <- subset(countData, select=-Frq08_DD24_rep3)

colData <- colData[!(colData$Sample=="Frq08_DD6_rep1"),]      
countData <- subset(countData, select=-Frq08_DD6_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD6_rep2"),]      
countData <- subset(countData, select=-Frq08_DD6_rep2)
colData <- colData[!(colData$Sample=="Frq08_DD6_rep3"),]      
countData <- subset(countData, select=-Frq08_DD6_rep3)
colData <- colData[!(colData$Sample=="Frq08_LL6_rep1"),]      
countData <- subset(countData, select=-Frq08_LL6_rep1)
colData <- colData[!(colData$Sample=="Frq08_LL6_rep2"),]      
countData <- subset(countData, select=-Frq08_LL6_rep2)
colData <- colData[!(colData$Sample=="Frq08_LL6_rep3"),]      
countData <- subset(countData, select=-Frq08_LL6_rep3)
colData <- colData[!(colData$Sample=="Frq08_DD12_rep1"),]      
countData <- subset(countData, select=-Frq08_DD12_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD12_rep2"),]      
countData <- subset(countData, select=-Frq08_DD12_rep2)
colData <- colData[!(colData$Sample=="Frq08_DD12_rep3"),]      
countData <- subset(countData, select=-Frq08_DD12_rep3)
colData <- colData[!(colData$Sample=="Frq08_DD18_rep1"),]      
countData <- subset(countData, select=-Frq08_DD18_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD18_rep2"),]      
countData <- subset(countData, select=-Frq08_DD18_rep2)
colData <- colData[!(colData$Sample=="Frq08_DD18_rep3"),]      
countData <- subset(countData, select=-Frq08_DD18_rep3)
colData <- colData[!(colData$Sample=="Frq08_DD24_rep1"),]      
countData <- subset(countData, select=-Frq08_DD24_rep1)
colData <- colData[!(colData$Sample=="Frq08_DD24_rep2"),]      
countData <- subset(countData, select=-Frq08_DD24_rep2)

colData <- colData[!(colData$Sample=="WT08_DD24_rep1"),]      
countData <- subset(countData, select=-WT08_DD24_rep1)
colData <- colData[!(colData$Sample=="WT08_DD24_rep2"),]      
countData <- subset(countData, select=-WT08_DD24_rep2)
colData <- colData[!(colData$Sample=="WT08_DD24_rep3"),]      
countData <- subset(countData, select=-WT08_DD24_rep3)
colData <- colData[!(colData$Sample=="WT08_DD18_rep1"),]      
countData <- subset(countData, select=-WT08_DD18_rep1)
colData <- colData[!(colData$Sample=="WT08_DD18_rep2"),]      
countData <- subset(countData, select=-WT08_DD18_rep2)
colData <- colData[!(colData$Sample=="WT08_DD18_rep3"),]      
countData <- subset(countData, select=-WT08_DD18_rep3)
colData <- colData[!(colData$Sample=="WT08_DD12_rep1"),]      
countData <- subset(countData, select=-WT08_DD12_rep1)
colData <- colData[!(colData$Sample=="WT08_DD12_rep2"),]      
countData <- subset(countData, select=-WT08_DD12_rep2)
colData <- colData[!(colData$Sample=="WT08_DD12_rep3"),]      
countData <- subset(countData, select=-WT08_DD12_rep3)
colData <- colData[!(colData$Sample=="WT08_DD6_rep1"),]      
countData <- subset(countData, select=-WT08_DD6_rep1)
colData <- colData[!(colData$Sample=="WT08_DD6_rep2"),]      
countData <- subset(countData, select=-WT08_DD6_rep2)
colData <- colData[!(colData$Sample=="WT08_DD6_rep3"),]      
countData <- subset(countData, select=-WT08_DD6_rep3)
colData <- colData[!(colData$Sample=="WT08_LL6_rep1"),]      
countData <- subset(countData, select=-WT08_LL6_rep1)
colData <- colData[!(colData$Sample=="WT08_LL6_rep2"),]      
countData <- subset(countData, select=-WT08_LL6_rep2)
colData <- colData[!(colData$Sample=="WT08_LL6_rep3"),]      
countData <- subset(countData, select=-WT08_LL6_rep3)



write.table(countData,"countData_53_Wc1",sep="\t",na="",quote=F)
write.table(colData,"colData_53_Wc1",sep="\t",na="",quote=F)


```

##Experiment samples 08

```R

require(DESeq2)
colData <- read.table("colData_08",header=T,sep="\t")
countData <- read.table("countData_08",header=T,sep="\t")
colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)
design <- ~Group

dds <- 	DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
#dds$Strain <- relevel(dds$Strain, "WT08")
dds <- DESeq(dds, fitType="local")
rld <- rlog( dds )

=================
PCA plots
=================
#Plot using rlog transformation:
plotPCA(rld,intgroup="Group")
plotPCA(rld,intgroup=c("Time","Group"))

#Plot using rlog transformation, showing sample names:
library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Group", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Group)) +
 geom_point(size=3) +
 theme_minimal()+
 theme(axis.title.x = element_text(size=30),
 axis.title.y = element_text(size=30),
 legend.text=element_text(size=20),
 legend.title=element_text(size=20),
 axis.text.x = element_text(colour="black",size=20),
 axis.text.y = element_text(colour="black",size=20),)+
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) + geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()

ggsave("PCA_sample_names.pdf", pca_plot, dpi=300, height=15, width=20)

#Plot using rlog transformation, showing sample names and elipses
library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Strain", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Strain, shape=Strain)) +
 geom_point(size=3) +
 theme_minimal()+
 theme(axis.title.x = element_text(size=30),
 axis.title.y = element_text(size=30),
 legend.text=element_text(size=20),
 legend.title=element_text(size=20),
 axis.text.x = element_text(colour="black",size=20),
 axis.text.y = element_text(colour="black",size=20),)+
 stat_ellipse(aes(x=PC1,y=PC2, fill=Strain),
              geom="polygon", level=0.95, alpha=0.2) +
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) +
 geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()
ggsave("PCA_sample_names_elipses.pdf", pca_plot, dpi=300, height=15, width=20)



=================
Sample distanes
=================

rld <- rlog( dds )
sampleDists <- dist( t( assay(rld) ) )
library("RColorBrewer")
sampleDistMatrix <- as.matrix( sampleDists )
rownames(sampleDistMatrix) <- paste(rld$Group)
colnames(sampleDistMatrix) <- paste(rld$Group)
colours = colorRampPalette( rev(brewer.pal(9, "Blues")) )(255)
heatmap( sampleDistMatrix, trace="none", col=colours)

dev.off()


===============
Analysis of gene expression
===============

##WT08 bl vs Frq08 bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","WT08bl06h","Frq08bl06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >1, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <1, ]

write.table(sig.res.upregulated,"WT08_Frq08_bl06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"WT08_Frq08_bl06h_down.txt",sep="\t",quote=F)
write.table(res,"WT08_Frq08_bl06h.txt",sep="\t",quote=F)

summary(res)


##WT08 d vs Frq08 d
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","WT08d06h","Frq08d06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"WT08_Frq08_d06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"WT08_Frq08_d06h_down.txt",sep="\t",quote=F)
write.table(res,"WT08_Frq08_d06h.txt",sep="\t",quote=F)

summary(res)


##Frq08 d vs Frq08 bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq08d06h","Frq08bl06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]


write.table(sig.res.upregulated,"Frq08_d_bl_06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq08_d_bl_06h_down.txt",sep="\t",quote=F)
write.table(res,"WT08_Frq08_d06h.txt",sep="\t",quote=F)

summary(res)


##WT08 d vs WT08 bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","WT08d06h","WT08bl06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]


write.table(sig.res.upregulated,"WT08_d_bl_06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt08_d_bl_06h_down.txt",sep="\t",quote=F)
write.table(res,"WT08_Frq08_d06h.txt",sep="\t",quote=F)

summary(res)

==================
Gene clustering
==================
#Gene clustering all samples 08
rld <- rlog( dds )
head( assay(rld) )

library("RColorBrewer")
library("gplots")
library( "genefilter" )

topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)
StrainCols <- brewer.pal(11, "RdGy")[c( 7,8, 9, 11)]
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="column", margins = c(5, 10), col = my_palette,par(lend = 1), cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Strain)])
legend("topright", levels(dds$Strain), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()


#Group the replicates
require(DESeq2)
colData <- read.table("colData_08",header=T,sep="\t")
countData <- read.table("countData_08",sep="\t",header=T,row.names=1)
colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)
design=~Group
dds <-   DESeqDataSetFromMatrix(countData,colData,~1)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds$groupby <- paste(dds$Group)
dds <- collapseReplicates(dds,groupby=dds$groupby)
design(dds) <- design
dds <- DESeq(dds,parallel=T)
rld <- rlog( dds )
head( assay(rld) )

#TopVarGenes
library("RColorBrewer")
library("gplots")
library( "genefilter" )
topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 200)
StrainCols <- brewer.pal(11, "RdGy")[c(7, 8, 9, 11)]
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 20), col = my_palette, cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Time)])
legend("topright", levels(dds$Time), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()


===============
Plotting results  
===============

plotCounts(dds, gene="VDAG_JR2_Chr1g01960", intgroup=c("Group"), normalized=TRUE)
dev.off()

```

##Experiment samples 53

```R

require(DESeq2)

colData <- read.table("colData_53",header=T,sep="\t")
countData <- read.table("countData_53",header=T,sep="\t")
colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)

colData <- colData[!(colData$Sample=="Frq53_LL6_rep2"),]      
countData <- subset(countData, select=-Frq53_LL6_rep2)
colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)

design <- ~Group
dds <- 	DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds <- DESeq(dds, fitType="local")
rld <- rlog( dds )



=================
PCA plots
=================
#Plot using rlog transformation:
plotPCA(rld,intgroup="Group")
plotPCA(rld,intgroup=c("Time","Group"))


#Plot using rlog transformation, showing sample names:
library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Group", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Group)) +
 geom_point(size=3) +
 theme_minimal()+
 theme(axis.title.x = element_text(size=30),
 axis.title.y = element_text(size=30),
 legend.text=element_text(size=20),
 legend.title=element_text(size=20),
 axis.text.x = element_text(colour="black",size=20),
 axis.text.y = element_text(colour="black",size=20),)+
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) + geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()

ggsave("PCA_sample_names.pdf", pca_plot, dpi=300, height=15, width=20)

#Plot using rlog transformation, showing sample names and elipses
library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Strain", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Strain, shape=Strain)) +
 geom_point(size=3) +
 theme_minimal()+
 theme(axis.title.x = element_text(size=30),
 axis.title.y = element_text(size=30),
 legend.text=element_text(size=20),
 legend.title=element_text(size=20),
 axis.text.x = element_text(colour="black",size=20),
 axis.text.y = element_text(colour="black",size=20),)+
 stat_ellipse(aes(x=PC1,y=PC2, fill=Strain),
              geom="polygon", level=0.95, alpha=0.2) +
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) +
 geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()
ggsave("PCA_sample_names_elipses.pdf", pca_plot, dpi=300, height=15, width=20)


=================
Sample distanes
=================

rld <- rlog( dds )
sampleDists <- dist( t( assay(rld) ) )
library("RColorBrewer")
sampleDistMatrix <- as.matrix( sampleDists )
rownames(sampleDistMatrix) <- paste(rld$Group)
colnames(sampleDistMatrix) <- paste(rld$Group)
colours = colorRampPalette( rev(brewer.pal(9, "Blues")) )(255)
heatmap( sampleDistMatrix, trace="none", col=colours)

dev.off()

===============
Analysis of gene expression
===============

##WT53 vs Wc153
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq53","53WT"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Wc153_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Wc153_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_Wc153.txt",sep="\t",quote=F)

summary(res)


##WT53 bl vs Wc153 bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Wc153bl06h","53WTbl06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Wc153_bl06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Wc153_bl06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_Wc153_bl06h.txt",sep="\t",quote=F)

summary(res)



##WT53 d vs Wc153 d
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Wc153d06h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Wc153_d06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Wc153_d06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_Wc153_d06h.txt",sep="\t",quote=F)



##WT53 bl vs Frq53 bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq53bl06h","53WTbl06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Frq53_bl06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Frq53_bl06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_Frq53_bl06h.txt",sep="\t",quote=F)

summary(res)

##WT53 d vs Frq53 d
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq53d06h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Frq53_d06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Frq53_d06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_Frq53_d06h.txt",sep="\t",quote=F)

summary(res)


##WT53 bl vs d
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTbl06h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_bl06h_vs_d06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_bl06h_vs_d06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_bl06h_vs_d06h.txt",sep="\t",quote=F)

summary(res)


##Wc153 d vs bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Wc153bl06h","Wc153d06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wc153_LD_06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wc153_LD_06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wc153_LD_06h.txt",sep="\t",quote=F)

summary(res)


##Frq53 d vs bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq53bl06h","Frq53d06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Frq53_LD_06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Frq53_LD_06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Frq53_LD_06h.txt",sep="\t",quote=F)

summary(res)

==================
Gene clustering
==================
#Group the replicates and remove outliers
require(DESeq2)
colData <- read.table("colData_53",header=T,sep="\t")
countData <- read.table("countData_53",sep="\t",header=T,row.names=1)

colData <- colData[!(colData$Sample=="Frq53_LL6_rep2"),]      
countData <- subset(countData, select=-Frq53_LL6_rep2)
colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)
design=~Group
dds <-   DESeqDataSetFromMatrix(countData,colData,~1)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds$groupby <- paste(dds$Group)
dds <- collapseReplicates(dds,groupby=dds$groupby)
design(dds) <- design
dds <- DESeq(dds,parallel=T)
rld <- rlog( dds )
head( assay(rld) )

#TopVarGenes
library("RColorBrewer")
library("gplots")
library( "genefilter" )
topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)

#Heatmap with ColSideColors
StrainCols <- brewer.pal(11, "RdGy")[c(7, 9, 11)]
my_palette <- colorRampPalette(c("red", "white", "darkblue"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 7), col = my_palette, cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Strain)])
legend("topright", levels(dds$Strain), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()


#Heatmap option 2
library("gplots")
library("devtools")

StrainCols <- sample(c("grey", "black", "lightgrey"), length(dds$Strain), replace=TRUE, prob=NULL)
LightCols <- sample(c("grey", "black"), length(dds$Light), replace=TRUE, prob=NULL)
TimeCols <- sample(c("grey", "black", "lightgrey", "darkred"), length(dds$Time), replace=TRUE, prob=NULL)
clab=cbind(StrainCols, LightCols, TimeCols)
colnames(clab)=c("Strain", "Light", "Time")
my_palette <- colorRampPalette(c("red", "black", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 7), cexCol=0.8,cexRow=0.4, ColSideColors=clab, col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()


#Pheatmap
library(pheatmap)
library(RColorBrewer)
library(viridis)

mat <- assay(rld)[ topVarGenes, ]
mat <- mat - rowMeans(mat)
df <- as.data.frame(colData(rld)[,c("Strain","Light")])
my_palette <- colorRampPalette(c("red", "white", "darkblue"))(n = 299)
pheatmap(mat, annotation_col=df, border_color=NA, scale="row", fontsize_row=3, col = my_palette, cluster_cols=FALSE)
dev.off()


===============
Plotting results  
===============
topGene <- rownames(res)[which.min(res$padj)]
plotCounts(dds, gene="VDAG_JR2_Chr1g01960", intgroup=c("Group"), normalized=TRUE)
dev.off()

```

##Experiment 53_Wc1

```R

require(DESeq2)

colData <- read.table("colData_53_Wc1",header=T,sep="\t")
countData <- read.table("countData_53_Wc1",header=T,sep="\t")
colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)

colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)

design <- ~Group
dds <- 	DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds <- DESeq(dds, fitType="local")
rld <- rlog( dds )

=================
PCA plots
=================
#Plot using rlog transformation:
plotPCA(rld,intgroup="Group")
plotPCA(rld,intgroup=c("Time","Group"))


#Plot using rlog transformation, showing sample names:
library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Group", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Group)) +
 geom_point(size=3) +
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) + geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()

ggsave("PCA_sample_names.pdf", pca_plot, dpi=300, height=15, width=20)


=================
Sample distanes
=================

rld <- rlog( dds )
sampleDists <- dist( t( assay(rld) ) )
library("RColorBrewer")
sampleDistMatrix <- as.matrix( sampleDists )
rownames(sampleDistMatrix) <- paste(rld$Group)
colnames(sampleDistMatrix) <- paste(rld$Group)
colours = colorRampPalette( rev(brewer.pal(9, "Blues")) )(255)
heatmap( sampleDistMatrix, trace="none", col=colours)

dev.off()

===============
Analysis of gene expression
===============

##WT53 bl vs Wc153 bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Wc153bl06h","53WTbl06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Wc153_bl06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Wc153_bl06h_down.txt",sep="\t",quote=F)
write.table(res,"Wt53_Wc153_bl06h.txt",sep="\t",quote=F)

summary(res)



##WT53 d vs Wc153 d
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Wc153d06h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated2 <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated2 <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Wc153_d06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Wc153_d06h_down.txt",sep="\t",quote=F)
write.table(res,"Wt53_Wc153_d06h.txt",sep="\t",quote=F)

summary(res)


==================
Gene clustering
==================
#Group the replicates and remove outliers
require(DESeq2)
colData <- read.table("colData_53",header=T,sep="\t")
countData <- read.table("countData_53",sep="\t",header=T,row.names=1)


colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)
design=~Group
dds <-   DESeqDataSetFromMatrix(countData,colData,~1)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds$groupby <- paste(dds$Group)
dds <- collapseReplicates(dds,groupby=dds$groupby)
design(dds) <- design
dds <- DESeq(dds,parallel=T)
rld <- rlog( dds )
head( assay(rld) )

#TopVarGenes
library("RColorBrewer")
library("gplots")
library( "genefilter" )
topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)

#Heatmap with ColSideColors
StrainCols <- brewer.pal(11, "RdGy")[c(7, 9, 11)]
my_palette <- colorRampPalette(c("red", "white", "darkblue"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 7), col = my_palette, cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Strain)])
legend("topright", levels(dds$Strain), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()
```


##Experiment 53_Frq

```R

require(DESeq2)

colData <- read.table("colData_53",header=T,sep="\t")
countData <- read.table("countData_53",header=T,sep="\t")
colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)

colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep1"),]      
countData <- subset(countData, select=-Wc153_DD6_rep1)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep2"),]      
countData <- subset(countData, select=-Wc153_DD6_rep2)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep3"),]      
countData <- subset(countData, select=-Wc153_DD6_rep3)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep1"),]      
countData <- subset(countData, select=-Wc153_LL6_rep1)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep2"),]      
countData <- subset(countData, select=-Wc153_LL6_rep2)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep3"),]      
countData <- subset(countData, select=-Wc153_LL6_rep3)

colData <- colData[!(colData$Sample=="Frq53_LL6_rep2"),]      
countData <- subset(countData, select=-Frq53_LL6_rep2)

design <- ~Group
dds <- 	DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds <- DESeq(dds, fitType="local")
rld <- rlog( dds )


=================
PCA plots
=================
#Plot using rlog transformation, showing sample names:
library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Group", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Group)) +
 geom_point(size=3) +
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) + geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()

ggsave("PCA_sample_names.pdf", pca_plot, dpi=300, height=15, width=20)


=================
Sample distanes
=================

rld <- rlog( dds )
sampleDists <- dist( t( assay(rld) ) )
library("RColorBrewer")
sampleDistMatrix <- as.matrix( sampleDists )
rownames(sampleDistMatrix) <- paste(rld$Group)
colnames(sampleDistMatrix) <- paste(rld$Group)
colours = colorRampPalette( rev(brewer.pal(9, "Blues")) )(255)
heatmap( sampleDistMatrix, trace="none", col=colours)

dev.off()

===============
Analysis of gene expression
===============

##WT53 bl vs Frq153 bl
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq53bl06h","53WTbl06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Frq53_bl06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Frq53_bl06h_down.txt",sep="\t",quote=F)
write.table(res,"Wt53_Frq53_bl06h.txt",sep="\t",quote=F)

summary(res)



##WT53 d vs Wc153 d
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","Frq53d06h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated2 <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated2 <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_Frq53_d06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_Frq53_d06h_down.txt",sep="\t",quote=F)
write.table(res,"Wt53_Frq53_d06h.txt",sep="\t",quote=F)

summary(res)


==================
Gene clustering
==================
#TopVarGenes without groupingby
library("RColorBrewer")
library("gplots")
library( "genefilter" )


topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)
StrainCols <- brewer.pal(11, "RdGy")[c(7, 9, 11)]
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 10), col = my_palette, cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Strain)])
legend("topright", levels(dds$Strain), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()


#Group the replicates and remove outliers
require(DESeq2)
colData <- read.table("colData_53",header=T,sep="\t")
countData <- read.table("countData_53",sep="\t",header=T,row.names=1)


colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep1"),]      
countData <- subset(countData, select=-Wc153_DD6_rep1)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep2"),]      
countData <- subset(countData, select=-Wc153_DD6_rep2)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep3"),]      
countData <- subset(countData, select=-Wc153_DD6_rep3)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep1"),]      
countData <- subset(countData, select=-Wc153_LL6_rep1)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep2"),]      
countData <- subset(countData, select=-Wc153_LL6_rep2)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep3"),]      
countData <- subset(countData, select=-Wc153_LL6_rep3)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep2"),]      
countData <- subset(countData, select=-Frq53_LL6_rep2)

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)
design=~Group
dds <-   DESeqDataSetFromMatrix(countData,colData,~1)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds$groupby <- paste(dds$Group)
dds <- collapseReplicates(dds,groupby=dds$groupby)
design(dds) <- design
dds <- DESeq(dds,parallel=T)
rld <- rlog( dds )
head( assay(rld) )

#TopVarGenes
library("RColorBrewer")
library("gplots")
library( "genefilter" )
topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)

#Heatmap with ColSideColors
StrainCols <- brewer.pal(11, "RdGy")[c(7, 9, 11)]
my_palette <- colorRampPalette(c("red", "ywllow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 7), col = my_palette, cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Strain)])
legend("topright", levels(dds$Strain), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()
```


##Experiment WT53 timecourse

```R

require(DESeq2)

colData <- read.table("colData_53",header=T,sep="\t")
countData <- read.table("countData_53",header=T,sep="\t")
colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)

colData <- colData[!(colData$Sample=="Frq53_DD6_rep1"),]      
countData <- subset(countData, select=-Frq53_DD6_rep1)
colData <- colData[!(colData$Sample=="Frq53_DD6_rep2"),]      
countData <- subset(countData, select=-Frq53_DD6_rep2)
colData <- colData[!(colData$Sample=="Frq53_DD6_rep3"),]      
countData <- subset(countData, select=-Frq53_DD6_rep3)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep1"),]      
countData <- subset(countData, select=-Frq53_LL6_rep1)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep2"),]      
countData <- subset(countData, select=-Frq53_LL6_rep2)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep3"),]      
countData <- subset(countData, select=-Frq53_LL6_rep3)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep1"),]      
countData <- subset(countData, select=-Wc153_DD6_rep1)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep2"),]      
countData <- subset(countData, select=-Wc153_DD6_rep2)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep3"),]      
countData <- subset(countData, select=-Wc153_DD6_rep3)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep1"),]      
countData <- subset(countData, select=-Wc153_LL6_rep1)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep2"),]      
countData <- subset(countData, select=-Wc153_LL6_rep2)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep3"),]      
countData <- subset(countData, select=-Wc153_LL6_rep3)

colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)

design <- ~Group
dds <- 	DESeqDataSetFromMatrix(countData,colData,design)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds <- DESeq(dds, fitType="local")
rld <- rlog( dds )


=================
PCA plots
=================
#Plot using rlog transformation, showing sample names:
library("ggplot2")
library("ggrepel")

data <- plotPCA(rld, intgroup="Group", returnData=TRUE)
percentVar <- round(100 * attr(data, "percentVar"))

pca_plot<- ggplot(data, aes(PC1, PC2, color=Group)) +
 geom_point(size=3) +
 xlab(paste0("PC1: ",percentVar[1],"% variance")) +
 ylab(paste0("PC2: ",percentVar[2],"% variance")) + geom_text_repel(aes(label=colnames(rld)))
 coord_fixed()

ggsave("PCA_sample_names.pdf", pca_plot, dpi=300, height=15, width=20)


=================
Sample distanes
=================

rld <- rlog( dds )
sampleDists <- dist( t( assay(rld) ) )
library("RColorBrewer")
sampleDistMatrix <- as.matrix( sampleDists )
rownames(sampleDistMatrix) <- paste(rld$Group)
colnames(sampleDistMatrix) <- paste(rld$Group)
colours = colorRampPalette( rev(brewer.pal(9, "Blues")) )(255)
heatmap( sampleDistMatrix, trace="none", col=colours)

dev.off()

===============
Analysis of gene expression
===============

##WT53 bl vs WT53 d
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTbl06h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.
sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_LD_06h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_LD_06h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_LD_06h.txt",sep="\t",quote=F)

summary(res)



##WT53 d06h vs WT53 d12h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd12h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_d06h_d12h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_d06h_d12h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_d06h_d12h.txt",sep="\t",quote=F)

summary(res)


##WT53 d06h vs WT53 d18h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd18h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_d06h_d18h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_d06h_d18h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_d06h_d18h.txt",sep="\t",quote=F)

summary(res)


##WT53 d06h vs WT53 d24h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd24h","53WTd06h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_d06h_d24h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_d06h_d24h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_d06h_d24h.txt",sep="\t",quote=F)

summary(res)


##WT53 d12h vs WT53 d24h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd24h","53WTd12h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_d12h_d24h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_d12h_d24h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_d12h_d24h.txt",sep="\t",quote=F)

summary(res)


##WT53 d12h vs WT53 d18h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd18h","53WTd12h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_d12h_d18h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_d12h_d18h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_d12h_d18h.txt",sep="\t",quote=F)

summary(res)


##WT53 d18h vs WT53 d24h
alpha <- 0.05
res= results(dds, alpha=alpha,contrast=c("Group","53WTd24h","53WTd18h"))

mcols(res, use.names=TRUE)

sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]
#Settings used: upregulated: min. 2x fold change, ie. log2foldchange min 1.
#               downregulated: min. 0.5x fold change, ie. log2foldchange max -1.

sig.res.upregulated <- sig.res[sig.res$log2FoldChange >0, ]
sig.res.downregulated <- sig.res[sig.res$log2FoldChange <0, ]

write.table(sig.res.upregulated,"Wt53_d24h_d18h_up.txt",sep="\t",quote=F)
write.table(sig.res.downregulated,"Wt53_d24h_d18h_down.txt",sep="\t",quote=F)
write.table(sig.res,"Wt53_d24h_d18h.txt",sep="\t",quote=F)

summary(res)


==================
Gene clustering
==================
#TopVarGenes without groupingby
library("RColorBrewer")
library("gplots")
library( "genefilter" )


topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 100)
StrainCols <- brewer.pal(11, "RdGy")[c( 7,8, 9, 11)]
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 10), col = my_palette, cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Time)])
legend("topright", levels(dds$Time), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()


#Group the replicates and remove outliers
require(DESeq2)
colData <- read.table("colData_53",header=T,sep="\t")
countData <- read.table("countData_53",sep="\t",header=T,row.names=1)


colData <- colData[!(colData$Sample=="Frq53_DD6_rep1"),]      
countData <- subset(countData, select=-Frq53_DD6_rep1)
colData <- colData[!(colData$Sample=="Frq53_DD6_rep2"),]      
countData <- subset(countData, select=-Frq53_DD6_rep2)
colData <- colData[!(colData$Sample=="Frq53_DD6_rep3"),]      
countData <- subset(countData, select=-Frq53_DD6_rep3)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep1"),]      
countData <- subset(countData, select=-Frq53_LL6_rep1)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep2"),]      
countData <- subset(countData, select=-Frq53_LL6_rep2)
colData <- colData[!(colData$Sample=="Frq53_LL6_rep3"),]      
countData <- subset(countData, select=-Frq53_LL6_rep3)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep1"),]      
countData <- subset(countData, select=-Wc153_DD6_rep1)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep2"),]      
countData <- subset(countData, select=-Wc153_DD6_rep2)
colData <- colData[!(colData$Sample=="Wc153_DD6_rep3"),]      
countData <- subset(countData, select=-Wc153_DD6_rep3)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep1"),]      
countData <- subset(countData, select=-Wc153_LL6_rep1)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep2"),]      
countData <- subset(countData, select=-Wc153_LL6_rep2)
colData <- colData[!(colData$Sample=="Wc153_LL6_rep3"),]      
countData <- subset(countData, select=-Wc153_LL6_rep3)

colData <- colData[!(colData$Sample=="WT53_DD18_rep3"),]      
countData <- subset(countData, select=-WT53_DD18_rep3)

colData$Group <- paste0(colData$Strain,colData$Light,colData$Time)
design=~Group
dds <-   DESeqDataSetFromMatrix(countData,colData,~1)
sizeFactors(dds) <- sizeFactors(estimateSizeFactors(dds))
dds$groupby <- paste(dds$Group)
dds <- collapseReplicates(dds,groupby=dds$groupby)
design(dds) <- design
dds <- DESeq(dds,parallel=T)
rld <- rlog( dds )
head( assay(rld) )

#TopVarGenes
library("RColorBrewer")
library("gplots")
library( "genefilter" )
topVarGenes <- head( order( rowVars( assay(rld) ), decreasing=TRUE ), 200)

#Heatmap with ColSideColors
StrainCols <- brewer.pal(11, "RdGy")[c(7, 8, 9, 11)]
my_palette <- colorRampPalette(c("red", "yellow", "green"))(n = 299)
heatmap.2( assay(rld)[ topVarGenes,], scale="row",
trace="none", dendrogram="row", margins = c(5, 20), col = my_palette, cexCol=0.8,cexRow=0.4,ColSideColors=StrainCols[unclass(dds$Time)])
legend("topright", levels(dds$Time), col = StrainCols, lty = 1, lwd = 5,
    cex = 0.5)
dev.off()


===============
Plotting results  
===============

res= results(dds, alpha=alpha,contrast=c("Group","53WTbl06h","53WTd06h"))
sig.res <- subset(res,padj<=alpha)
sig.res <- sig.res[order(sig.res$padj),]

topGene <- rownames(res)[which.min(res$padj)]
plotCounts(dds, gene="VDAG_JR2_Chr2g01990", intgroup=c("Group"), normalized=TRUE)
dev.off()

```

#Make a table of raw counts, normalised counts and fpkm values:

```R
raw_counts <- data.frame(counts(dds, normalized=FALSE))
colnames(raw_counts) <- paste(colData$Group)
write.table(raw_counts,"raw_counts.txt",sep="\t",na="",quote=F)
norm_counts <- data.frame(counts(dds, normalized=TRUE))
colnames(norm_counts) <- paste(colData$Group)
write.table(norm_counts,"normalised_counts.txt",sep="\t",na="",quote=F)

## When the raw_data is created, the column names are shifted, due to the lack of column name for the genes. To fx it, do nano filex, and then added the word "Gene", press tab and save ctr+x


install.packages("XVector", Sys.getenv("R_LIBS_USER"), repos = "http://cran.case.edu" )

library(XVector)
library(Biostrings)
library(naturalsort)
mygenes <- readDNAStringSet("/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/public_genomes/JR2/Verticillium_dahliaejr2.VDAG_JR2v.4.0.cds.all.fa")
t1 <- counts(dds)
t1 <- mygenes[rownames(t1)]
rowRanges(dds) <- GRanges(t1@ranges@NAMES,t1@ranges)



# robust may be better set at fasle to normalise based on total counts rather than 'library normalisation factors'
#Maria produced the FPKM files
fpkm_counts <- data.frame(fpkm(dds, robust = TRUE))
colnames(fpkm_counts) <- paste(colData$Group)
write.table(fpkm_counts,"fpkm_norm_counts.txt",sep="\t",na="",quote=F)
fpkm_counts <- data.frame(fpkm(dds, robust = FALSE))
colnames(fpkm_counts) <- paste(colData$Group)
write.table(fpkm_counts,"fpkm_counts.txt",sep="\t",na="",quote=F)
```

#Produce a detailed table of analyses
'''python
This program parses information from fasta files and gff files for the location,
sequence and functional information for annotated gene models and RxLRs.
'''

```
Run with commands:

for GeneGff in $(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.33_parsed.gff3); do
    Strain=JR2
    Organism=V.dahliae
    Assembly=$(ls public_genomes/JR2/Verticillium_dahliaejr2.GCA_000400815.2.dna.toplevel.fa)
    InterPro=$(ls /home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/gene_pred/interproscan/V.dahliae/JR2/JR2_interproscan.tsv)
    SwissProt=$(ls /home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/gene_pred/swissprot/V.dahliae/12008/swissprot_vJul2016_tophit_parsed.tbl)
    OutDir=gene_pred/annotation/$Organism/$Strain
    mkdir -p $OutDir
    GeneFasta=$(ls public_genomes/JR2/Verticillium_dahliaejr2.VDAG_JR2v.4.0.cds.all.fa)
    Dir1=$(ls -d RNA_alignment/featureCounts/experiment_53)
    Dir2=$(ls -d RNA_alignment/featureCounts/experiment_53/WT53)
    DEG_Files=$(ls \
        $Dir1/Frq53_LD_06h.txt \
        $Dir1/Wc153_LD_06h.txt \
        $Dir1/Wt53_Frq53_bl06h.txt \
        $Dir1/Wt53_Frq53_d06h.txt \
        $Dir1/Wt53_bl06h_vs_d06h.txt \
        $Dir1/Wt53_Wc153_bl06h.txt \
        $Dir1/Wt53_Wc153_d06h.txt \
        $Dir2/Wt53_d06h_d12h.txt \
        $Dir2/Wt53_d06h_d18h.txt \
        $Dir2/Wt53_d06h_d24h.txt \
        $Dir2/Wt53_d12h_d18h.txt \
        $Dir2/Wt53_d12h_d24h.txt \
        $Dir2/Wt53_d24h_d18h.txt \
        $Dir2/Wt53_LD_06h.txt \
        | sed -e "s/$/ /g" | tr -d "\n")

    RawCount=$(ls $Dir1/raw_counts_53.txt)
    FPKM=$(ls $Dir1/countData_53.fpkm)
    ProgDir=/home/armita/git_repos/emr_repos/scripts/verticillium_clocks/annotation
    $ProgDir/Vd_annotation_tables.py --gene_gff $GeneGff --gene_fasta $GeneFasta --DEG_files $DEG_Files --raw_counts $RawCount --fpkm $FPKM --InterPro $InterPro --Swissprot $SwissProt > $OutDir/"$Strain"_gene_table_incl_exp.tsv
done

```

#Draw venn diagrams of differenitally expressed genes

##All genes

###All DEGs

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=Wt53_Wc153_bl06h.txt
inp2=Wt53_Frq53_bl06h.txt
OutDir=Wc1bl_vs_Frqbl_all_DEGs.tsv
$ProgDir/parse_RNASeq_2-way.py --input_1 $inp1 --input_2 $inp2 --out_file $OutDir
```

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=Wt53_Wc153_d06h.txt
inp2=Wt53_Frq53_d06h.txt
OutDir=Wc1d_vs_Frqd_all_DEGs.tsv
$ProgDir/parse_RNASeq_2-way.py --input_1 $inp1 --input_2 $inp2 --out_file $OutDir
```

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=WT53/Wt53_d06h_d12h.txt
inp2=WT53/Wt53_d06h_d18h.txt
inp3=WT53/Wt53_d06h_d24h.txt
OutDir=Wt53_timelapse_all_DEGs.tsv
$ProgDir/parse_RNASeq_3-way.py --input_1 $inp1 --input_2 $inp2 --input_3 $inp3 --out_file $OutDir
```

###Upregulated DEGs

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=Wt53_Wc153_bl06h_up.txt
inp2=Wt53_Frq53_bl06h_up.txt
OutDir=Wc1bl_vs_Frqbl_up_DEGs.tsv
$ProgDir/parse_RNASeq_2-way.py --input_1 $inp1 --input_2 $inp2 --out_file $OutDir
```

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=Wt53_Wc153_d06h_up.txt
inp2=Wt53_Frq53_d06h_up.txt
OutDir=Wc1d_vs_Frqd_up_DEGs.tsv
$ProgDir/parse_RNASeq_2-way.py --input_1 $inp1 --input_2 $inp2 --out_file $OutDir
```

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=WT53/Wt53_d06h_d12h_up.txt
inp2=WT53/Wt53_d06h_d18h_up.txt
inp3=WT53/Wt53_d06h_d24h_up.txt
OutDir=Wt53_timelapse_up_DEGs.tsv
$ProgDir/parse_RNASeq_3-way.py --input_1 $inp1 --input_2 $inp2 --input_3 $inp3 --out_file $OutDir
```
###Downregulated DEGs

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=Wt53_Wc153_bl06h_down.txt
inp2=Wt53_Frq53_bl06h_down.txt
OutDir=Wc1bl_vs_Frqbl_down_DEGs.tsv
$ProgDir/parse_RNASeq_2-way.py --input_1 $inp1 --input_2 $inp2 --out_file $OutDir
```

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=Wt53_Wc153_d06h_down.txt
inp2=Wt53_Frq53_d06h_down.txt
OutDir=Wc1d_vs_Frqd_down_DEGs.tsv
$ProgDir/parse_RNASeq_2-way.py --input_1 $inp1 --input_2 $inp2 --out_file $OutDir
```

```
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
inp1=WT53/Wt53_d06h_d12h_down.txt
inp2=WT53/Wt53_d06h_d18h_down.txt
inp3=WT53/Wt53_d06h_d24h_down.txt
OutDir=Wt53_timelapse_down_DEGs.tsv
$ProgDir/parse_RNASeq_3-way.py --input_1 $inp1 --input_2 $inp2 --input_3 $inp3 --out_file $OutDir
```


###Venn diagrams
#Mutants in light
ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
WorkDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/featureCounts/experiment_53
$ProgDir/All_DEGs_venn_diag_2.r  --inp $WorkDir/Wc1bl_vs_Frqbl_all_DEGs.tsv --out $WorkDir/Wc1bl_Frqbl_all_DEGs.pdf
$ProgDir/All_DEGs_venn_diag_2.r --inp $WorkDir/Wc1bl_vs_Frqbl_up_DEGs.tsv --out $WorkDir/Wc1bl_Frqbl_up_DEGs.pdf
$ProgDir/All_DEGs_venn_diag_2.r --inp $WorkDir/Wc1bl_vs_Frqbl_down_DEGs.tsv --out $WorkDir/Wc1bl_Frqbl_down_DEGs.pdf

#Timecourse WT

ProgDir=/home/lopeze/git_repos/scripts/verticillium_clocks
WorkDir=/home/groups/harrisonlab/project_files/verticillium_dahliae/clocks/RNA_alignment/featureCounts/experiment_53
$ProgDir/All_DEGs_venn_diag.r --inp $WorkDir/Wt53_timelapse_all_DEGs.tsv --out $WorkDir/Wt53_timelapse_all_DEGs.pdf
$ProgDir/All_DEGs_venn_diag.r --inp $WorkDir/Wt53_timelapse_up_DEGs.tsv --out $WorkDir/Wt53_timelapse_up_DEGs.pdf
$ProgDir/All_DEGs_venn_diag.r --inp $WorkDir/Wt53_timelapse_down_DEGs.tsv --out $WorkDir/Wt53_timelapse_down_DEGs.pdf



##Investigate enriched functional annotations in DEGs vs all genes

##Analysis of DEGs vs all genes

OutDir=analysis/enrichment/experiment_53/Whole_Genome
mkdir -p $OutDir
InterProTSV=/home/groups/harrisonlab/project_files/verticillium_dahliae/pathogenomics/gene_pred/interproscan/V.dahliae/JR2/JR2_interproscan.tsv
ProgDir=/home/adamst/git_repos/scripts/fusarium/analysis/gene_enrichment
$ProgDir/GO_prep_table.py --interpro $InterProTSV > $OutDir/experiment_53_gene_GO_annots.tsv

ProgDir=/home/adamst/git_repos/scripts/phytophthora_fragariae
AnnotTable=gene_pred/annotation/V.dahliae/JR2/JR2_gene_table_incl_exp.tsv
DEGs=alignment/star/P.fragariae/Bc16/DeSeq/Bc16_all_DEGs_names.txt
AllGenes=$OutDir/Bc16_all_genes.txt
cat $AnnotTable | tail -n+2  | cut -f1 > $AllGenes
Set1Genes=$OutDir/Bc16_DEGs.txt
Set2Genes=$OutDir/Bc16_all_genes2.txt
AllGenes=$OutDir/Bc16_all_genes.txt
cat $DEGs | sed -e 's/$/\t0.001/g' > $Set1Genes
cat $AnnotTable | tail -n+2 | cut -f1 | grep -v $Set1Genes | sed -e 's/$/\t1.00/g' > $Set2Genes
cat $Set1Genes $Set2Genes > $AllGenes

$ProgDir/GO_enrichment.r --all_genes $AllGenes --GO_annotations $OutDir/Bc16_gene_GO_annots.tsv --out_dir $OutDir > $OutDir/output.txt
