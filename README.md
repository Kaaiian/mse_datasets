# mse_datasets
A repository with data for various materials properties. Data and/or references are provided. Scripts for processing the data are provided.

## THINGS TO DO:
0. (Read Matbench paper to get idea about different types of materials tasks)
1. For each data, make a script to process the "raw data".
2. Return a "CSV" file with all missing data.
3. If data has "ICSD/OQMD/MP id numbers, make sure these values aren't lost"
4. Get the MP data that is missing.
5. Get more experimental tasks? Get more "interesting non MP/OQMD tasks"


## BENCHMARK DATA:
Data CSV's


## Data Origins:


**CritcalExaminationStability_Data**

    preprint: A critical examination of compound stability predictions from machine-learned formation energies
    preprint url: https://arxiv.org/ftp/arxiv/papers/2001/2001.10591.pdf
    code url: https://github.com/CJBartel/TestStabilityML
    data url: https://github.com/CJBartel/TestStabilityML/blob/master/mlstabilitytest/mp_data/data/hullout.json

    Brief description:
        Ef → ML models trained on formation energies. (material project)
        Ed → ML models trained on decomposition energies.


**IRNet_Data (& ElemNet)**

    print, ElemNet: Deep Learning the Chemistry of Materials From Only Elemental Composition
    print url: https://www.nature.com/articles/s41598-018-35934-y
    code url: https://github.com/NU-CUCIS/ElemNet


    preprint, IRNet: A General Purpose Deep Residual Regression Framework for Materials Discovery
    preprint url: https://arxiv.org/pdf/1907.03222.pdf
    code url: https://github.com/NU-CUCIS/IRNet


    data url: https://github.com/NU-CUCIS/IRNet/tree/master/training-data
    data OQMD-C: http://cucis.ece.northwestern.edu/projects/DataSets/IRNet/training-data/oqmd-c.csv


    Brief description:

        OQMD-C data is provided with the repository.

        MP-C Data is not provided on either repository, however MatMiner data (url: https://hackingmaterials.lbl.gov/matminer/dataset_summary.html) (date: 10/18/2018, Number of entries: 83989) matches statistics reported in paper.
        **TODO: Get MP data and targets from matminer using python API**

        "MP-C is composed of 83989 inorganic compounds from the Materials Project database with a set of materials properties as of September 2018"

        Performance from paper (Test errors are MAE in eV/atom.)
        Dataset Property | Best of 10 ML | 17-layer Plain Network | 17-layer IRNet | 48-layer IRNet
        OQMD-C
        Formation Enthalpy 0.077 0.072 0.054 0.048
        Bandgap 0.047 0.052 0.051 0.047
        Energy per atom 0.1139 0.0939 0.0696 -
        Volume pa 0.473 0.0.483 0.415 0.394
        MP-C
        Bandgap 0.4788 0.396 0.363 0.364
        Density 0.5052 0.401 0.348 0.386
        Energy above hull 0.1184 0.098 0.091 0.0944
        Energy per atom 0.2999 0.175 0.143 -
        Total magnetization 3.232 3.0897 3.005 -
        Volume 225.671 219.439 215.037 -


**Matbench_Data**

    preprint: Benchmarking Materials Property Prediction Methods: The Matbench Test Set and Automatminer Reference Algorithm
    preprint url: https://arxiv.org/ftp/arxiv/papers/2005/2005.00707.pdf
    code url: None
    data url: https://hackingmaterials.lbl.gov/automatminer/datasets.html#down-loading-datasets
    data other location: https://github.com/hackingmaterials/automatminer + python script

    Brief description:
        13 materials prediction tasks. See preprint (pg. 5) for description of each.


**Roost_Data**

    preprint: Benchmarking Materials Property Prediction Methods: The Matbench Test Set and Automatminer Reference Algorithm
    preprint url: https://arxiv.org/pdf/1910.00617.pdf
    code url: https://github.com/CompRhys/roost
    data url: https://github.com/CompRhys/roost/tree/bec6f7a5f87eb6cb63669349169619a8d48890ce/data/datasets NOTE: This is data from an older commit. Some data was removed from the repository since it was unused in the preprint.

    Brief description:
    Dataset sources (no additional information given)
        OQMD
        The Open Quantum Materials Database (OQMD) http://oqmd.org/

        Materials Project
        The Materials Project (MP) https://materialsproject.org/

        SuperCon
        Superconducting Material Database (SuperCon) https://supercon.nims.go.jp/

        Experimental Bandgaps
        Predicting the Band Gaps of Inorganic Solids by Machine Learning https://pubs.acs.org/doi/10.1021/acs.jpclett.8b00124


**AFLOW_Data**

    print: Benchmark AFLOW Data Sets for Machine Learning
    print url: free link (https://rdcu.be/b4sgn), https://link.springer.com/article/10.1007/s40192-020-00174-4,
    code url: https://github.com/oconradh/benchmark_aflow
    data url: https://doi.org/10.6084/m9.figshare.11954742

    Brief description:
        A collection of *unprocessed* properties from AFLOW database.

        Data was extracted from downloaded zip.
        The following properties were selected from the zip files "processed_data" folder for learning:
            - ael_bulk_modulus_vrh
            - ael_shear_modulus_vrh
            - ael_debye_temperature
            - agl_thermal_conductivity_300K
            - agl_thermal_expansion_300K
            - Egap
            - energy_atom
        These files were moved to the repository with no modifications. The script "process.py" was then run.
        The following data were removed as a result.
            **TODO: ADD LIST OF THINGS THAT ARE REMOVED.**
