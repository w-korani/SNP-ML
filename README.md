# SNP-ML is A machine learning dependent tool for SNP calling in polyploidy organisms

Korani, W. A.; Clevenger, J.;  Chu, Y. and Ozias-Akins, P. (2019). Machine Learning as an Effective Method for Identifying True Single Nucleotide Polymorphisms in Polyploid Plants. Plant Genome, 12(1).

# this program requires the following packages:
*   numpy-1.11.0 (SciPy.org) https://pypi.python.org/pypi/numpy/1.11.0
*   scipy-0.17.1 (SciPy.org) https://pypi.python.org/pypi/scikit-learn/0.17.1
*   pandas-0.18.1 (pandas.pydata.org) https://pypi.python.org/pypi/pandas/0.18.1/
*   python-dateutil-2.0 (pypi.python.org) http://labix.org/python-dateutil
*   pytz-2016.4 (pypi.python.org) https://pypi.python.org/pypi/pytz/2016.4
*   scikit-learn-0.17.1 (scikit-learn.org) https://pypi.python.org/pypi/scikit-learn/0.17.1
*   pyrenn 0.1 (pyrenn.readthedocs.io) https://pyrenn.readthedocs.io/en/latest/

the user can check if s/he has any of these package/versions by running the python command:

pip list|grep package_name
      
      example: pip list|grep scipy

If any of these pacakges are not availble, it should be downloaded and installed before running SNP-ML.
the user may use the following command to directly install a specific package: 

pip install 'package==version' 
      
      example: pip install 'numpy==1.11.0'

After downloading and extracting SNP-ML, the user probably needs to run chmod command if s/he has a permission issue, EXAMPLE: chmod 777 SNP-ML

# the program takes vcf file as input, the input file can be SWEEP output or the output of calling SNPs by samtools mpileup or any other tools, in case of using samtools/bcftools, the user should use -m option (not -c) when he/she calls SNPs, EXAMPLE:
1.   samtools faidx reference.fa
2.   samtools mpileup -g -f reference.fa genotype1.bam genotype2.bam genotype3.bam > output.bcf
3.   bcftools call -vc -V indels output.bcf > output_snps.bcf
4.   bcftools convert output_snps.bcf -o output_snps_input4snpml.vcf

# the program was tested and works fine with samtools 1.2 and bcftools 1.2.1
# help file containing the information for running the program can be retrieve by typing SNP-ML -h or SNP-MLer -h
# testing vcf is available in the extracted files, dna_test.vcf, it can be run by the following command as examples:
      ./SNP-ML -i DNA_test.vcf -iM peanut_DNA -o output_test

      ./SNP-ML -i DNA_test.vcf -iM sim_peanut_two_10x -o output_test
# creating a new model command examples:
      ./SNP-MLer -iTP TP_five_genotype_10x_snps.vcf -iFP FP_five_genotype_10x_snps.vcf -o sim_peanut_five_10x

NOTE: An extendable database is available (db), the user can donwload the desired database into the 'db' folder of SNP-ML.
