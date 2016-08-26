# SNP-ML is A machine learning dependent tool for SNP calling in polyploidy organisms
# this program requirs the following packages:
  numpy-1.11.0 (SciPy.org)
  scipy-0.17.1 (SciPy.org)
  pandas-0.18.1 (pandas.pydata.org)
  python-dateutil-2.0 (pypi.python.org)
  pytz-2016.4 (pypi.python.org)
  scikit-learn-0.17.1 (scikit-learn.org) 
  pyrenn 0.1 (pyrenn.readthedocs.io)
# SNP-ML.tar.gz can be downoloaded and extracted (tar -zxvf SNP-ML.tar.gz) in advance, then if the user does not have requried packages, dependencies.tar.gz can be downloaded and extracted (tar -zxvf dependencies.tar.gz), it will create a folder called "dependencies" inside SNP-ML folder, the contents can be installed by running dep.sh file.
# the program takes vcf file as input, the input file can be SWEEP output or the output of calling SNPs by samtools mpileup, in case of using samtools/bcftools, the user should use -m option (not -c) when he/she calls SNPs, EXAMPLE:
  samtools faidx refernce.fa
  samtools mpileup -g -f refernce.fa genotype1.bam genotype2.bam genotype3.bam > output.bcf
  bcftools call -vc -V indels output.bcf > output_snps.bcf
  bcftools convert output_snps.bcf -o output_snps_input4snpml.vcf
# the program was tested and works fine with samtools 1.2 and bcftools 1.2.1
# help file containing the information for running the program can be retrieve by typing SNP-ML -h
