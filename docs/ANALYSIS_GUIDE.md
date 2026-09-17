# FASTA Sequence Analyzer - Analysis Guide

## Available Analyses
| Analysis | Description | Input |
|----------|-------------|-------|
| GC Content | Calculate GC percentage | DNA/RNA |
| Motif Search | Find sequence patterns | DNA/Protein |
| Restriction Sites | Find enzyme cut sites | DNA |
| Composition | Amino acid/nucleotide stats | Any |

## Example: Analyzing a FASTA File
```python
from fasta_analyzer import FASTAAnalyzer

analyzer = FASTAAnalyzer("sequences.fasta")

# GC Content
gc = analyzer.gc_content()
print(f"GC Content: {gc:.2f}%")

# Find motifs
sites = analyzer.find_motif("GAATTC")  # EcoRI
print(f"Found {len(sites)} EcoRI sites")

# Full report
analyzer.generate_report("output.txt")
```

## Restriction Enzymes Supported
| Enzyme | Recognition Site | Cut Pattern |
|--------|-----------------|-------------|
| EcoRI | GAATTC | G^AATTC |
| BamHI | GGATCC | G^GATCC |
| HindIII | AAGCTT | A^AGCTT |
| NotI | GCGGCCGC | GC^GGCCGC |

## Output Format
Reports include: sequence length, GC%, nucleotide composition,
identified motifs with positions, and restriction site mapping.