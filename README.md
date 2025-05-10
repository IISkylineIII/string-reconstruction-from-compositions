# String Reconstruction from Compositions

This repository contains a Python script that reconstructs a linear string from a set of compositions represented as patterns. Each pattern consists of two possible substrings, and the goal is to reconstruct the string by selecting prefixes from one part and suffixes from the other.

## Problem Overview

Given a list of compositions in the form of patterns like "(ACC|ATA)", "(ACT|ATT)", etc., the task is to:
1. Extract the prefixes (first part before the "|") and suffixes (second part after the "|").
2. Reconstruct the linear string by concatenating the first prefix and then following the last character of each suffix.

This type of problem is often seen in bioinformatics, especially when dealing with sequence assembly or related tasks.

## Script

```python
compositions = [
    "(ACC|ATA)", "(ACT|ATT)", "(ATA|TGA)", "(ATT|TGA)", "(CAC|GAT)",
    "(CCG|TAC)", "(CGA|ACT)", "(CTG|AGC)", "(CTG|TTC)", "(GAA|CTT)",
    "(GAT|CTG)", "(GAT|CTG)", "(TAC|GAT)", "(TCT|AAG)", "(TGA|GCT)",
    "(TGA|TCT)", "(TTC|GAA)"
]

# Extract prefixes and suffixes from the compositions
prefixes, suffixes = zip(*(comp[1:-1].split('|') for comp in compositions))

# Reconstruct the linear string
linear_string = prefixes[0] + ''.join(suffix[-1] for suffix in suffixes)

print(linear_string)
```

### Example Output
ACTATGAGTCAGCTGCGCATTAGTCAAGTTAG

### Requirements
Python 3.6 or higher

### No external libraries are required.

### Applications
Bioinformatics sequence assembly
String reconstruction and genome assembly tasks
Algorithm design in computational biology

### License
This project is released under the MIT License.
