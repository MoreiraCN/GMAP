### GMAP

The following pipeline was used for mapping and aligning cDNA sequences on the assembled genome of the species *Holochilus sciureus* (2n = 56, NF = 56), a Neotropical rodent of tribe Oryzomyini.

**Softwares used:**

[gmap-v2019-09-12](http://research-pub.gene.com/gmap/). Wu TD, Watanabe CK (2005) GMAP: a genomic mapping and alignment program for mRNA and EST sequences. Bioinformatics, 21(9):1859-1875.

**Input data:**

- [Assembled](https://github.com/MoreiraCN/Assembling_Illumina_sequences) genome in fasta format.
- Transcripts file from a reference species ([Mus_musculus.GRCm38.cds.all.fa](http://ftp.ensembl.org/pub/release-104/fasta/mus_musculus/cds/)).

**Step 1 > Index build:**

`/gmap_build  -D index_folder -d sample_name assembly.fa`

**Step 2 > Mapping and aligning:**

`/gmap -t 20 -D index_folder -p 1 --gff3-add-separators=0 -n 1 --min-trimmed-coverage=0.70 --min-identity=0.90 --nofails -f gff3_gene -d sample_name transcripts_file.cds.all.fa > output_file.gff3`

**Parameters used:**

- All parameters used are available at [GMAP manual](http://research-pub.gene.com/gmap/src/README).
