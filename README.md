# Codon Table Generator

# Project Overview

The **Codon Table Generator** is a Python-based project that generates and uses the standard genetic code to translate nucleotide sequences into amino acid sequences.

The program accepts DNA and RNA sequences, validates the input, divides the sequence into codons (triplets of nucleotides), and translates each codon into its corresponding amino acid.

It also identifies start and stop codons, handles incomplete codons, and compares the generated codon table with the NCBI Standard Genetic Code.

# Objectives

- Generate a standard genetic code dictionary containing all 64 codons.
- Accept and validate DNA and RNA sequences.
- Divide nucleotide sequences into groups of three bases.
- Translate codons into their corresponding amino acids.
- Identify start and stop codons.
- Detect incomplete codons.
- Display translation results in a tabular format.
- Validate codon assignments by comparing them with the NCBI reference.
- Translate RNA sequences to DNA sequences in a similar manner
# Features

1. Codon Table Generation

Each DNA codon is mapped to its corresponding amino acid using its single-letter amino acid code.

The dictionary contains all 64 possible codons, including the three stop codons.

2. DNA Sequence Validation

The program accepts a DNA sequence and checks whether it contains only valid DNA nucleotides:

- Adenine (A)
- Thymine (T)
- Guanine (G)
- Cytosine (C)

Invalid sequences are rejected.

3. RNA Sequence Validation and Translation

The program also supports RNA sequences containing:

- Adenine (A)
- Uracil (U)
- Guanine (G)
- Cytosine (C)

For translation, the RNA sequence is converted into its corresponding DNA-equivalent sequence by replacing U with T. This allows the existing DNA codon dictionary to be used for RNA translation.

4. Codon Splitting

The nucleotide sequence is divided into groups of three bases.

Each group represents a codon, which is subsequently used for amino acid translation.

5. Amino Acid Translation

Each codon is matched against the codon dictionary to determine its corresponding amino acid.

The resulting amino acid sequence is displayed to the user.

6. Start and Stop Codon Identification

The program identifies:

- **Start codon:** ATG
- **Stop codons:** TAA, TAG and TGA

Their positions within the input sequence are reported and enumerated.

7. Incomplete Codon Handling

Nucleotide sequences may contain leftover bases that do not form a complete triplet.

The program identifies incomplete codons separately rather than treating them as valid codons.

8. Tabular Output

The translation results are displayed in a structured table containing:

| Position | Codon | Amino Acid |
|---|---|---|
| 1 | ATG | Methionine |
| 2 | GCT | Alanine |
| 3 | TTT | Phenylalanine |

*Example output; amino acid representation depends on the selected codon dictionary.*

9. Comparison with NCBI Reference

The generated codon table is compared against the NCBI Standard Genetic Code (Translation Table 1).

Biopython is used to retrieve the reference codon assignments. The comparison identifies matching, mismatching and missing codons.

This provides a way to verify the accuracy of the generated codon table.

Technologies and Libraries

- Python: Programming language.
- Jupyter Notebook: Development and execution environment.
- Biopython: Retrieval of the NCBI standard genetic code reference table.

#Installation and Execution

1. Install Python

Ensure that Python is installed on your system.

2. Install Biopython

Run the following command in a Jupyter Notebook cell:

3. Import the required library
from Bio.Data import CodonTable

4. Load the NCBI reference table
reference_table = CodonTable.unambiguous_dna_by_id[1]

5. Run the notebook

Execute the notebook cells in sequence, starting with the codon dictionary and function definitions, followed by sequence input, translation and reference comparison.

Example
Input RNA sequence:AUGUGUU

Expected codons:ATG, TGT, U

Expected translation: M, C, Incomplete codon

The final nucleotide is reported as an incomplete codon because it does not form a complete triplet.

#Reference

National Center for Biotechnology Information (NCBI).

[The Genetic Codes – Translation Table 1: Standard Code](https://www.ncbi.nlm.nih.gov/Taxonomy/Utils/wprintgc.cgi)

Biopython documentation:

[Biopython – Codon Tables](https://biopython.org/docs/latest/api/Bio.Data.CodonTable.html)

# Limitations

- The program uses the standard genetic code and does not currently account for alternative genetic codes.
- Translation is performed from the beginning of the supplied sequence rather than identifying complete open reading frames.
- Start and stop codon identification does not independently establish whether a biologically functional protein is produced.

# Future Improvements

- Support for alternative genetic codes.
- Identification of open reading frames (ORFs).
- Improved output formatting and visualisation.
- Additional testing with different nucleotide sequences.
- Support for reading and translating sequence files in FASTA format.

# Author

Developed as a Python programming project to explore codon mapping, nucleotide sequence translation and basic bioinformatics concepts.
