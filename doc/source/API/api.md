# shuffle function
```
def shuffle(k=None, s=None, l=None, o=None):
    """
       Generate a k-mer substring space shuffled file.

       Args:
           k (int): Half-length of k-mer. k=x means using k-mer of length 2x.
           s (int): Half-length of k-mer substring. s=x means the whole space is the collection of all 2x-mers. Make sure l < s < k. Default is -s 6, usually there's no need to change this setting.
           l (int): The level of dimensionality-reduction. l=x means the expected rate of dimensionality-reduction is 16^x.
           o (str): Output filename of the .shuf file.

       Returns:
           bool: True

       Example:
           >>> kssdtree.shuffle(k=10, s=6, l=3, o='L3K10.shuf')
           True
            
    """
    return True
```
# sketch function
```
def sketch(shuf_file=None, genome_files=None, output=None, abundance=None, set_opt=None):
    """

       Sketch genomes and generate sketch files.

       Args:
           shuf_file (str): Path to the .shuf file. Kssdtree provides optional .shuf files which specifies different parameters of k-mer length and dimensionality-reduction level ('L3K9.shuf', 'L3K10.shuf', etc.) . If the .shuf file does not exist in current path, it will be automatically generated or downloaded. Default .shuf file is 'L3K10.shuf'. Other .shuf files will automatically generated by called shuffle function.
           genome_files (str): Path for the genome files. Kssdtree supports genome files of both fasta or fastq format.
           output (str): Output folder path for the sketch generated.
           abundance (str): Perform species profiling for fastq file if needed. Default is False. To perform profiling, set abundance=True.
           set_opt (bool): Perform set operations (subtract and retrieve) if needed. Default is False. To perform set operations, set set_opt=True.

       Returns:
           bool: True

       Example:
           >>> kssdutils.sketch(shuf_file='L3K10.shuf', genome_files='ES29', output='ES29_sketch')
           True
           >>> kssdutils.sketch(shuf_file='../shuf_file/L3K10.shuf', genome_files='../data/ES29', output='ES29_sketch', set_opt =True)
           True
           >>> kssdutils.sketch(shuf_file='L3K10.shuf', genome_files='ERR011350.fastq', output='ERR011350_sketch', abundance=True, set_opt =True)
           True
    """
    return True
```
# dist function
```
def dist(ref_sketch=None, qry_sketch=None, output=None, metric=None, N=None, flag=None):
    """

       Compute the distance matrix between query genome sketches and reference genome sketches.

       Args:
           ref_sketch (str): Path to the folder of reference genome sketches.
           qry_sketch (str): Path to the folder of query genome sketches.
           output (str): Filename for the output distance matrix. The .phylip (.phy) format is generally used to  build phylogenetic tree using NJ,DNJ, and FastME. The .mat format is generally used to perform phylogenetic placement using APPLES.  It is required ref_sketch and qry_sketch is same in .phylip (.phy) format for output. It is required ref_sketch and qry_sketch is different in .mat format for output.
           metric (str): Metric for distance estimation (Mash distance: metric=’mash’ or AAF distance: metric=’aaf’).
           N (int): Maximum number of nearest reference genomes to retrieve.
           flag (int): When create .phylip (.phy) format distance matrix for build phylogenetic tree,Specifies the way to generate the distance matrix, where 0 is for NJ algorithm (with zeros on the diagonal), 1 is for DNJ algorithm (without the diagonal elements) and 2 is for FastME algorithm.

       Returns:
           bool: True

       Example:
           #Calculate distance create matrix for building phylogenetic tree in NJ method, using Mash distance
           >>> kssdutils.dist(ref_sketch='ES29_sketch', qry_sketch='ES29_sketch', output='ES29.phylip', metric ='mash', flag=0)
           True
           #Calculate distance create matrix for building phylogenetic tree in NJ method, using AAF distance
           >>> kssdutils.dist(ref_sketch='ES29_sketch', qry_sketch='ES29_sketch', output='ES29.phylip', metric ='aaf', flag=0)
           True
           #Calculate distance and create matrix for performing phylogenetic placement in APPLES method
           >>> kssdutils.dist(ref_sketch='ref_sketch', qry_sketch='qry_sketch', output='qry.mat', metric ='mash')
           True
           # Calculate distance between qry_sketch and ref_sketch and by specifying query number N
           >>> kssdutils.dist(ref_sketch='markerdb.gtdbr220_L3K10_sketch', qry_sketch='ERR011350_sketch', output='ERR011350.mat', N=10, metric='mash')
           True
           ERR011350.mat:
        1697_Eisenbergiella_tayi        216_Barnesiella_intestinihominis        1281_Clostridium_A_leptum       7075_Butyrivibrio_A_crossotus   2038_Ruthenibacterium_lactatiformans
ERR011350       0.247869        0.281590        0.280658        0.282390        0.286652
    """
    return True
```

