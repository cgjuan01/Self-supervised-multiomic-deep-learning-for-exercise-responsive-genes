This repository contains the full implementation of exercise-only, multi-omic Trait Efficiency Loci Graph Neural Network (TEL GNN) designed to identify exercise-responsive, multi-layer regulatory genes.

The model integrates:

Proteomic MR (UKBB → PPP plasma proteins)

Epigenomic mQTL / DNAm features

Glycomic / gQTL features

Transcriptomic bulk + single-cell eQTL features

Exercise-TEL (TEL_ex) cross-omic summary features

Glycan-pathway prior (FUT8, ST6GAL1, B4GALT1, etc.)

and learns a graph-structured representation of exercise biology using self-supervised contrastive GNN pretraining, with optional supervised evaluation.

🔍 What This Model Does

✔ 1. Self-Supervised Contrastive GNN (SimCLR-style)

No labels required

Two augmented feature-dropout “views”

Trains a GCN encoder to maximise agreement between augmented node embeddings

Produces:

GNN_exercise_score_ssl

GNN_exercise_rank_ssl

✔ 2. Optional Supervised GNN

Activated only if you pass:

--label_col <binary_column>


The script will:

Train a GCN classifier

Compare SSL+linear probe vs fully supervised GNN

Output:

GNN_exercise_score_sup

GNN_exercise_rank_sup
