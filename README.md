# Biney's Procedural Compression

The proposed method, referred to as Biney’s Procedural Compression, aims to find the smallest possible program capable of reconstructing a file losslessly. Rather than representing a file directly as compressed data, the compressor attempts to discover a compact procedural description of the file.

A procedural description consists of:

- An algorithm.
- A seed (or set of parameters).

Executing the algorithm together with its seed should reproduce the original file exactly. The objective is therefore to discover, as efficiently as possible, the smallest program capable of reconstructing the original data without loss. If the resulting procedural description is substantially smaller than the original file, it serves as the compressed representation.

This concept is closely related to Kolmogorov complexity, which studies the length of the shortest program capable of generating a given string. Since the exact shortest program is not computable in the general case, the objective is instead to search for practical approximations under realistic computational constraints.

Example constraints include:

- Maximum program size ≤ K bytes.
- Reconstruction time ≤ T.
- Search time or computational budget ≤ C.

Within these constraints, the compressor searches for the best procedural representation it can find. (Read the PDFs—they explain the idea from scratch and consolidate everything discussed so far.)

The core idea is to treat lossless compression as a search problem: instead of encoding a file directly, search for the smallest procedural description (an algorithm + seed/parameters) that reconstructs the original file losslessly.

The MAIN goal is to explore whether this idea can be made computationally feasible and practically useful while achieving better compression ratios than existing compression algorithms for very large datasets, such as archives, servers, data centers, relational databases, and other long-term storage. It is NOT intended to replace fast, everyday compression algorithms, but rather to investigate a potential archival-scale compression approach that seeks higher compression ratios than existing methods by deliberately trading compression time and computational resources for improved compression efficiency.

---

## Documents

All proposal documents (PDFs, notes, and related files) are located in the `docs/` directory.

```text
docs/
├── proposal-v1.pdf                              # Main proposal
├── optimization-notes.pdf                       # Optimization ideas
├── notation-clarifications.pdf                  # Notation and terminology
├── future-directions.pdf                        # Additional research notes
└── Biney's Procedural Compression_v1.md/pdf     # Most recent complete paper v1
```

Please read the PDFs—they explain the idea from scratch in detail and consolidate everything discussed so far.
