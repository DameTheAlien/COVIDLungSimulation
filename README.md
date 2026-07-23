# COVID Simulation #

📄 **Project Report**

[Modeling the Adaptive Immune Response to SARS-CoV-2 by Modifying SIM-CoV Report](./Project2_MTDF.pdf)

This is a model for simulating the response of the immune system to infections in the lungs.

## Installing and building

It requires [UPC++](https://bitbucket.org/berkeleylab/upcxx/wiki/Home), C++ and cmake.

This repo contains a submodule, so to install, it's best to run

`git clone --recurse-submodules git@github.com:AdaptiveComputationLab/simcov.git`

to fully initialize the submodules.

Once downloaded, build it with

`./build.sh Release`

or

`./build.sh Debug`

The executable will be installed in

`<simcov-repo-directory>/install/bin`

## Running

To run, execute

`upcxx-run -n <number_processes> -N <number_nodes> -- simcov`

To see the parameters available, run with `-h`.

It will create an output directory, which will contain a detailed log file (`simcov.log`). It will also create a file containing
all the configuration parameters (`simcov.config`).

A run can also be executed with a config file as

`upcxx-run -n <number_processes> -N <number_nodes> -- simcov --config <config_file>`

The config file consists of a list of all the command line options as key-value pairs, with semi-colons denoting comments.
For example:

```
; Dimensions: x y z
  dim =                    100,100,100

; Number of timesteps
  timesteps =                   14000

```
