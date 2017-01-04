# LM2PM
This is a package to transfer genetic distance data from plink .map format files across to your own SNP data.

The pipeline is invoked using Python 3, with the toy data running as: python lm2pm.py -l new -o old -n new.map

-o: The plink .map file is shown in the sample data "old" and consists of 4 tab separated columns and ordered as: Chromosome (chr), SNP name (rs), genetic distance (morg) and base pair (bp).

-l: Your own data, consisting of SNP locations, in the order of: Chromosome (chr) and base pair (bp).
Files shouldn't have a header

-n: The new file contains all SNPs in plink .map format. If you want to obtain a file containing your own SNP locations alone, simply run the following, where rs is a string commonly found in the SNP names of the downloaded plink.map file:
grep -v "rs" new.map > new1.map

Should iterpolation of genetic distance be required, this can be achieved by removing the hases of the pandas option later on in the script. You can use the toy data to check the behaviour.
