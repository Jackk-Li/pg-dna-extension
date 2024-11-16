# DNA Sequence Database Extension

This project is a PostgreSQL extension for storing and analyzing DNA sequences, focusing on k-mer analysis. The extension implements custom data types, functions, and a trie-based index for efficient DNA sequence operations. It is designed as part of the INFO-H417 Database System Architecture course project.

## Features
1. **Custom Data Types**:
   - `dna`: Represents DNA sequences with no length limit.
   - `kmer`: Represents subsequences of DNA (k-mers) with a max length of 32.
   - `qkmer`: Represents queryable k-mers using IUPAC nucleotide codes.

2. **Functions and Operators**:
   - `length(type)`: Returns the length of DNA, kmer, or qkmer.
   - `generate_kmers(sequence, k)`: Generates all k-mers from a DNA sequence.
   - `equals(kmer1, kmer2)`: Checks equality between k-mers.
   - `starts_with(kmer, prefix)`: Checks if a k-mer starts with a specific prefix.
   - `contains(qkmer, kmer)`: Checks if a k-mer matches a qkmer pattern.

3. **K-mer Counting Support**:
   - Supports grouping, counting, and querying k-mers efficiently.

4. **SP-GiST Index Implementation**:
   - Supports equality, prefix, and pattern matching queries for k-mers.

## Project Structure

dna-sequence-extension/
├── src/                    # Source code
│   ├── dna.c               # DNA type implementation
│   ├── kmer.c              # kmer type implementation
│   ├── qkmer.c             # qkmer type implementation
│   └── spgist_index.c      # SP-GiST index implementation
├── sql/                    # SQL scripts
│   ├── create_extension.sql # Create the extension
│   └── test_extension.sql   # Test the extension
├── tests/                  # Unit tests
│   └── dna_test.c          # Tests for DNA type
├── docs/                   # Documentation
│   └── presentation.pptx   # Presentation slides
├── .github/                # GitHub configuration
│   └── workflows/ci.yml    # CI configuration
└── README.md               # Project documentation
