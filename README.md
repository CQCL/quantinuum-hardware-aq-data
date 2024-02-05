# quantinuum-hardware-AQ-data
This repository contains data from algorithmic qubits benchmarking on Quantinuum hardware. 


## Project Organization
------------

    ├── README.md          
    └── /data               <- Algorithmic qubit data

--------

## Getting Started

Each data directory contains the summary information from each set of circuits (e.g. `Amplitude Estimation_summary_info.json`) where the data is saved a dictionary with the following form

```
{
    "n=<n>, <param>=<value>": {
        "description": [<n>, <param>],
        "qasm": "OPENQASM 2.0;...",
        "ideal output": {'0001': 1.0,...},
        "machine output": {'0001': 425,...},
        "voted output": {'0001': 500,...},
    }
    ...
}
```

Where `<n>`=qubit number, `<param>` = circuit parameters to specify circuit in QED-C code, `"qasm"` = exact qasm submitted to quantinuum machine with compilation, `"ideal output"` = ideal outputs specified by QED-C code, `"machine output"` = measured output from quantinuum machine, `"voted output"` = outputs after apply plurality voting. 

Each data set can also be loaded and plotted by cloning the [Algorithmic Qubits fork of the QED-C rep](https://github.com/ionq/QC-App-Oriented-Benchmarks/tree/ionq/aq) and copying the `DATA-....json` file from this repo into the data directory of the cloned repo. Then run the `aq-qiskit.ipynb` notebook's final cell with the `backend_id` replaced by the name of the `DATA-....json` file copied over.
