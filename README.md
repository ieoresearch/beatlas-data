# beatlas data

Reference data downloaded by the **beatlas** desktop app the first time it starts. beatlas lists every
editing outcome of the guides of a base editing library and annotates it on genes, proteins, ClinVar
and protein domains. The analysis runs on the user's computer: libraries and results never leave it.

This repository contains **only data releases**, assembled from public sources. There is no code here.
The app checks every file against the SHA-256 written in its own data catalog before using it.

## Release data-2026.10

| File | Content | Size |
|---|---|---|
| `reference-hg38_mane1.5_appris2026_06_cv20261011_up2026_03.tar.gz` | ClinVar 2026-10-11 (single-base variants, GRCh38), MANE Select 1.5 and APPRIS 2026_06 transcript ranking, UniProt 2026_03 human reviewed entries and features | 59 MB |
| `structures-afdb_v6_long_fragments.tar.gz` | AlphaFold DB v6 models of the 214 human proteins longer than 2,700 residues (fragments, one in five) | 228 MB |
| `ppi-ppi_string12.5_biogrid.tar.gz` | Physical protein interactions: STRING 12.5 (score ≥ 400) and BioGRID multi-validated pairs | 4 MB |
| `BSgenome.Hsapiens.UCSC.hg38_1.4.5.tar.gz` | Human genome sequence GRCh38/hg38 (Bioconductor 3.22 package, unchanged) | 731 MB |
| `TxDb.Hsapiens.UCSC.hg38.knownGene_3.22.0.tar.gz` | Gene annotation, UCSC knownGene (Bioconductor 3.22 package, unchanged) | 60 MB |
| `org.Hs.eg.db_3.22.0.tar.gz` | Gene identifiers and symbols (Bioconductor 3.22 package, unchanged) | 105 MB |

The three Bioconductor packages are byte-for-byte the files published by Bioconductor (same MD5); they are
mirrored here so that the first launch of the app does not depend on the speed of a single server. If this
repository cannot be reached, the app downloads them from bioconductor.org.

Checksums: `SHA256SUMS` in each release.

## Sources, licences and citations

Each dataset keeps the licence of its source. Please cite the sources when you use results based on them.

| Data | Source | Licence | Citation |
|---|---|---|---|
| ClinVar | NCBI | public domain (NCBI data policy) | Landrum MJ et al. Nucleic Acids Res 2018 |
| MANE Select | NCBI / EMBL-EBI | freely available | Morales J et al. Nature 2022 |
| APPRIS | CNIO | see appris.bioinfo.cnio.es | Rodriguez JM et al. Nucleic Acids Res 2022 |
| UniProtKB/Swiss-Prot | UniProt Consortium | CC BY 4.0 | UniProt Consortium, Nucleic Acids Res 2025 |
| AlphaFold DB | EMBL-EBI / Google DeepMind | CC BY 4.0 | Varadi M et al. Nucleic Acids Res 2024 |
| STRING | STRING consortium | CC BY 4.0 | Szklarczyk D et al. Nucleic Acids Res 2023 |
| BioGRID | BioGRID | MIT | Oughtred R et al. Protein Sci 2021 |
| BSgenome, TxDb, org.Hs.eg.db | Bioconductor (data from UCSC and NCBI) | Artistic-2.0 | Huber W et al. Nat Methods 2015 |

The files were reformatted for beatlas (for example: ClinVar reduced to single-base variants and to the
fields used, AlphaFold models split into fragments); the content is otherwise unchanged. Each archive
contains a `manifest.json` with the exact source versions and checksums.

## Not for clinical use

beatlas and these data are for research. Predicted editing outcomes are possibilities, not measured
frequencies, and the annotations are not a clinical interpretation.
