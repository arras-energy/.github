# Welcome to Arras Energy

Arras Energy is the commercial release of HiPAS GridLAB-D supported and distributed by LF Energy.

The following options are available for using Arras Energy:

## Run on Docker

~~~
docker run -it -v $PWD:/model slacgismo/gridlabd:latest gridlabd -W /model [LOADOPTIONS] [FILENAME.EXT] [RUNOPTIONS]
~~~

## Run on AWS

1. Sign into your AWS console.
2. Launch an EC2 instance.
3. Search the community AMI for images starting with `gridlabd` in the `us-west-1` (N. California) region.
4. Choose an instance type with sufficient memory, e.g., >4GB.
5. Download and save your keypair.
6. Launch the instance.
7. Connect to the instance.
8. Download your model into the instance, e.g., from GitHub.
9. Run the simulation using the usual command line options.
10. Save the results, e.g., to GitHub.

## Download on Mac, Windows WSL, or Ubuntu Linux

~~~
curl -sL http://install.gridlabd.us/install.sh | [sudo] sh
~~~

## Build your own

~~~
git clone https://code.gridlabd.us/ [-b BRANCH] gridlabd
cd gridlabd
./setup.sh --local
./build.sh --system --validate
~~~

# Current Project Status

| Repository | Build | Deploy |
| :---: | :---: | :---: |
| [GridLAB-D](https://github.com/slacgismo/gridlabd) | ![master](https://github.com/slacgismo/gridlabd/actions/workflows/master.yml/badge.svg?branch=master) ![develop](https://github.com/slacgismo/gridlabd/workflows/develop/badge.svg?branch=develop) | [![master-images](https://github.com/slacgismo/gridlabd/actions/workflows/master-image.yml/badge.svg)](https://github.com/slacgismo/gridlabd/actions/workflows/master-image.yml) [![develop-images](https://github.com/slacgismo/gridlabd/actions/workflows/develop-image.yml/badge.svg)](https://github.com/slacgismo/gridlabd/actions/workflows/develop-image.yml) |
| [Templates](https://github.com/slacgismo/gridlabd-template) | [![master](https://github.com/slacgismo/gridlabd-template/actions/workflows/master.yml/badge.svg)](https://github.com/slacgismo/gridlabd-template/actions/workflows/master.yml) [![develop](https://github.com/slacgismo/gridlabd-template/actions/workflows/develop.yml/badge.svg)](https://github.com/slacgismo/gridlabd-template/actions/workflows/develop.yml)
| [Weather](https://github.com/slacgismo/gridlabd-weather) | [![validate](https://github.com/slacgismo/gridlabd-weather/actions/workflows/validate.yml/badge.svg)](https://github.com/slacgismo/gridlabd-weather/actions/workflows/validate.yml)
| [Library](https://github.com/slacgismo/gridlabd-library) | [![validate](https://github.com/slacgismo/gridlabd-library/actions/workflows/master.yml/badge.svg)](https://github.com/slacgismo/gridlabd-library/actions/workflows/master.yml) [![validate](https://github.com/slacgismo/gridlabd-library/actions/workflows/develop.yml/badge.svg)](https://github.com/slacgismo/gridlabd-library/actions/workflows/develop.yml)
| [Models](https://github.com/slacgismo/gridlabd-models) | [![validate](https://github.com/slacgismo/gridlabd-models/actions/workflows/validate.yml/badge.svg)](https://github.com/slacgismo/gridlabd-models/actions/workflows/validate.yml)
| [Benchmarks](https://github.com/slacgismo/gridlabd-benchmarks) | Manual test (see [README.md](https://github.com/slacgismo/gridlabd-benchmarks/blob/main/README.md))
| [Examples](https://github.com/slacgismo/gridlabd-examples) | Manual test (see [README.md](https://github.com/slacgismo/gridlabd-examples/blob/master/README.md))

The documentation for this project is located at http://docs.gridlabd.us/.

This respository contains the source code to Arras Energy, which was developed by SLAC National Accelerator Laboratory for the California Energy Commission under a grant for [HiPAS GridLAB-D](https://www.energizeinnovation.fund/projects/hipas-gridlab-d-high-performance-agent-based-simulation-using-gridlab-d) ([EPC-17-046](https://www.energy.ca.gov/filebrowser/download/1147)).  Arras Energy is the commercial version of the [US Department of Energy's research version of GridLAB-D developed by Pacific Northwest National Laboratory](https://github.com/gridlab-d/gridlab-d).
