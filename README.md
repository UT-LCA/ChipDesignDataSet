# FPGA_ML_DATASET
This is the datasets used for fpga performance evaluation via machine learning. It contains thousands of verilog designs which can be used to train machine learning model and perform performance prediction.
It contains two categories according to the source of programs: HLS_dataset and Verilog_dataset.

## HLS_dataset
It contains verilog designs generated from C program via high level synthesis. We refered to https://github.com/zlinaf/PowerGear and extended their methods to apply to varities of C benchmark to increase the diversities of verilog designs. This repo summarize how the generated verilog design look like while it does not contain the actual generated verilog designs, for the actualy verilog designs downloading, please refer to the below links.

polybench:
chstone:
machsuite:

Noted that in each tar ball, it contains:
1. verilog files and tcl scripts which can be used directly in vivado
2. IR codes(.bc), IR operator information(.adb), FSMD mdoel(.adb.xml), HLS report(.rpt, .rpt.xml) generated from HLS

## Verilog_dataset
It contains verilog designs collected from different domains. It contains only raw designs for now.

## File Architecture
    .
    ├── HLS_dataset                           # machine learning dataset for high level synthesis, Verilog designs generated from C codes
    │   ├── polybench                         # benchmark name
    │   │   ├── atax                          # kernel name
    │   │   │   ├── scripts                   # tcl scripts to run hls, synthesis, implementation and evaluation
    │   │   │   ├── src                       # source code in C which is marked with hls pragma
    │   │   │   ├── testbench                 # testbenches in verilog to test generated designs
    │   │   │   ├── xczu9eg-ffvb1156-2-i      # contains a info.csv file to summarize the generated verilog designs targeting xczu9eg
    │   │   │   └── xc7v585tffg1157-3         # contains a info.csv file to summarize the generated verilog designs targeting xc7v585
    │   │   ├── bicg
    │   │   ├── gemm
    │   │   ├── gesummv
    │   │   ├── k2mm
    │   │   ├── k3mm
    │   │   ├── mvt
    │   │   ├── syr2k
    │   │   └── syrk
    │   └── chstone                           # work in progress, it contains only C code now
    │   └── machsuite                         # work in progress, it contains only C code now
    └── Verilog_dataset                       # Veriog designs, work in progress
        ├── opencores                         
        ├── vtr_designs
        └── yosys_designs
        

## Todo
5. upload tar balls on lca/zenodo
6. udpate the csv files

