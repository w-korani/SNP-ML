# SNP-ML is A machine learning dependent tool for SNP calling in polyploidy organisms
# this program requirs the following packages:
 *  numpy-1.11.0 (SciPy.org) https://pypi.python.org/pypi/numpy/1.11.0
*   scipy-0.17.1 (SciPy.org) https://pypi.python.org/pypi/scikit-learn/0.17.1
*   pandas-0.18.1 (pandas.pydata.org) https://pypi.python.org/pypi/pandas/0.18.1/
*   python-dateutil-2.0 (pypi.python.org) http://labix.org/python-dateutil
*   pytz-2016.4 (pypi.python.org) https://pypi.python.org/pypi/pytz/2016.4
*   scikit-learn-0.17.1 (scikit-learn.org) https://pypi.python.org/pypi/scikit-learn/0.17.1
*   pyrenn 0.1 (pyrenn.readthedocs.io) https://pyrenn.readthedocs.io/en/latest/
the user can check if s/he has any of these package/versions by running the python command:
print("\n".join(sorted(["%s==%s" % (i.key, i.version) for i in pip.get_installed_distributions()])))

If any of these pacakges are not availble, it should be downloaded and installed before running SNP-ML.
After downloading and extracting SNP-ML, the user probably needs to run chmod command if s/he has a permission issue, EXAMPL: chmod 777 SNP-ML

# the program takes vcf file as input, the input file can be SWEEP output or the output of calling SNPs by samtools mpileup or any other tools, in case of using samtools/bcftools, the user should use -m option (not -c) when he/she calls SNPs, EXAMPLE:
1.   samtools faidx refernce.fa
2.   samtools mpileup -g -f refernce.fa genotype1.bam genotype2.bam genotype3.bam > output.bcf
3.   bcftools call -vc -V indels output.bcf > output_snps.bcf
4.   bcftools convert output_snps.bcf -o output_snps_input4snpml.vcf

# the program was tested and works fine with samtools 1.2 and bcftools 1.2.1
# help file containing the information for running the program can be retrieve by typing SNP-ML -h
# testing vcf is available in the extracted files, dna_test.vcf, it can be run by the following command as an example:
SNP-ML -i input_dna4test.vcf -o output_test -c 0.5 -t dna
