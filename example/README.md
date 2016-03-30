# LoLoPicker

#Installation
#####git clone https://github.com/jcarrotzhang/LoLoPicker
#####cd LoLoPicker
#####python setup.py install
######dependencies pysam (>=0.8.4) pysamstats
######Please note that LoLoPicker is no longer available on PyPI

#Step one: calling raw, somatic variants using matched tumor/normal

python LoLoPicker_somatic.py -t tumor.bam -n normal.bam -r reference.fa -b interval.bed (e.g. CCDS_in_bed_format) -o outputpath

#Step two: inspecting your control cohort

python LoLoPicker_control.py -l samplelist.txt -r reference.fa -n thread -o outputpath

#####please provide your control panel in samplelist.txt using the following tab-delimited format:
######Bam_file_of_each_control      \t      control_sampleID

#Step three: performing core stats

python LoLoPicker_stats.py -o outputpath

#####For analyzing whole-genome sequencing data, please use the -b option and split your job by genomic intervals (e.g. chromosomes).
