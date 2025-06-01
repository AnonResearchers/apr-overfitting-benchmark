# Empirical Evaluation of Patch Overfitting Detection Approaches in Automated Program Repair
This is the replication package for "Empirical Evaluation of Patch Overfitting Detection Approaches in Automated Program Repair".

## Directory Structure

```
apr-overfitting-benchmark/
├── datasets/
│   ├── petke/ # classical dataset
│   │   ├── all_patches/ # All classical dataset patches before deduplication
│   │   └── patches_by_time/ # Classical dataset patches grouped by discovery time.
│   └── repairllama/ # repairllama dataset
│       ├── context_size_3_evaluation_defects4j_repairllama_ir4_or2_martin/ # Original dataset
│       ├── context_size_3_filtered/ # Filtered dataset for our experiments
│       ├── repairllama_filtering.py # Filtering script
│       └── README.md # Explaining the source of the patches and filtering script
│── defects4j_projects/ # Defects4J projects required to replicate experiments for each dataset
│   ├── petke/ 
│   ├── repairllama/
│   ├── checkout_d4j.py # Script to download all necessary buggy and fixed Defects4J projects (see below)
│   └── README.md # Explaining the usage of checkout_d4j.py
│── figure_replication/
│   ├── combined_figures/ # Raw data, tables and visualisations for classical and repairllama datasets combined 
│   ├── petke_1h_figures/ # Raw data, tables and visualisations for classical (1h APR tool runtime)
│   ├── petke_8h_figures/ # Raw data, tables and visualisations for classical dataset
│   ├── repairllama_figures/ # Raw data, tables and visualisations for repairllama dataset
│   ├── scripts/ # Scripts used to analyse the classifications in results/
│   ├── figure-replication-requirements.txt # Requirements for analysis replication
│   └── README.md # Instructions to replicate data analysis
│── results/
│   └── ... # Sub-directories for each overfitting detector containing classification results on all datasets
│── tools/
│   ├── ... # Sub-directories for each overfitting detector with modified source code used for benchmarking
│   └── README.md # Detailed instructions for each tool on how to replicate experiments
└── README.md # You are here!
```

## Study Replication

1. **Checkout Defects4J Projects**  
   Use the provided script [`defects4j_projects/checkout_d4j.py`](defects4j_projects/checkout_d4j.py) to automatically download all necessary buggy and fixed project versions. See the README in [`defects4j_projects/`](defects4j_projects/) for more information.

   > **Note:** This requires Defects4J to be installed and configured. Defects4J depends on Java 11. You must update the `JAVA_11_PATH` constant in `checkout_d4j.py` to point to a valid Java 11 installation.  
   > For setup instructions, refer to the [Defects4J GitHub repository](https://github.com/rjust/defects4j).

2. **Run Evaluation Tools**  
   Follow the setup and usage instructions provided in [`tools/README.md`](tools/README.md) to run the evaluation tools and move outputs to the `results/` directory as described.

3. **Replicate Figures**  
   After obtaining all experimental outputs, replicate the figures and tables by following the instructions in [`figure_replication/README.md`](figure_replication/README.md).