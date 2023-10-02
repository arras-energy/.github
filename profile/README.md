# Welcome to The Linux Foundation's Arras Energy Project

Arras Energy is the commercial-grade release of [HiPAS GridLAB-D](https://www.energizeinnovation.fund/projects/hipas-gridlab-d-high-performance-agent-based-simulation-using-gridlab-d) supported and distributed by [Linux Foundation Energy](https://lfenergy.org).

The documentation for this project is located at http://docs.gridlabd.us/.

This organization contains the source code and support repositories to Arras Energy, which was developed by [SLAC National Accelerator Laboratory](https://slac.stanford.edu) for the [California Energy Commission](https://www.energy.ca.gov) under grant [EPC-17-046](https://www.energy.ca.gov/filebrowser/download/1147).  This version of GridLAB-D is a commercial-grade version of the [US Department of Energy's research version of GridLAB-D developed by Pacific Northwest National Laboratory](https://github.com/gridlab-d/gridlab-d).

*Note*: This fork of [GridLAB-D](https://github.com/gridlab-d/gridlab-d) does not support MS Windows directly. You must use docker or a virtual machine running linux.

The following options are available for using Arras Energy:

## Run on GitHub

You can run Arras Energy with GitHub Actions using the template https://github.com/gridlabd-tutorials/.new_project. The simulation results are stored in a downloadable file that can accessed from the `Actions` tab in your GitHub project. A tutorial for using Arras Energy with GitHub is available at https://github.com/gridlabd-tutorials.

## Run on Docker

~~~
docker run -it -v $PWD:/model lfenergy/arras:latest gridlabd -W /model [LOADOPTIONS] [FILENAME.EXT] [RUNOPTIONS]
~~~

See [Dockerhub HiPAS repositories](https://hub.docker.com/r/hipas/gridlabd/tags) for a list of available images.

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

You can also start the instance from the command line:

~~~
aws ec2 run-instances --image-id AMINAME --count 1 --instance-type INSTANCETYPE --key-name KEYPAIRNAME --security-group-ids SECURITYGROUPID --subnet-id SUBNETID
~~~

You can search the [AWS AMI Catalog](https://us-west-1.console.aws.amazon.com/ec2/home?AMICatalog%3A=&region=us-west-1#AMICatalog:) for Community AMIs matching "Arras Energy HiPAS GridLAB-D" in the `us-west-1` region. The version number will be included in the name.

## Download on Mac, Windows WSL, or Ubuntu Linux

~~~
curl -sL https://install.gridlabd.us/install.sh | [sudo] sh
~~~

## Build your own

~~~
git clone https://source.gridlabd.us/ [-b BRANCH] gridlabd
cd gridlabd
./setup.sh --local
./build.sh --system --validate
~~~

### Access remote resources

HiPAS GridLAB-D requires access to many remote resources. To ensure that access is possible, please verify that your site supports the [HiPAS GridLAB-D cybersecurity plan](/CYBERSECURITY.md).

# Current Project Status

| Repository | Build | Deploy |
| :---: | :---: | :---: |
| [GridLAB-D](https://github.com/arras-energy/gridlabd) | ![master](https://github.com/arras-energy/gridlabd/actions/workflows/master.yml/badge.svg?branch=master) ![develop](https://github.com/arras-energy/gridlabd/workflows/develop/badge.svg?branch=develop) | [![master-images](https://github.com/arras-energy/gridlabd/actions/workflows/master-image.yml/badge.svg)](https://github.com/arras-energy/gridlabd/actions/workflows/master-image.yml) [![develop-images](https://github.com/arras-energy/gridlabd/actions/workflows/develop-image.yml/badge.svg)](https://github.com/arras-energy/gridlabd/actions/workflows/develop-image.yml) |
| [Templates](https://github.com/arras-energy/gridlabd-template) | [![master](https://github.com/arras-energy/gridlabd-template/actions/workflows/master.yml/badge.svg)](https://github.com/arras-energy/gridlabd-template/actions/workflows/master.yml) [![develop](https://github.com/arras-energy/gridlabd-template/actions/workflows/develop.yml/badge.svg)](https://github.com/arras-energy/gridlabd-template/actions/workflows/develop.yml)
| [Weather](https://github.com/arras-energy/gridlabd-weather) | [![validate](https://github.com/arras-energy/gridlabd-weather/actions/workflows/validate.yml/badge.svg)](https://github.com/arras-energy/gridlabd-weather/actions/workflows/validate.yml)
| [Library](https://github.com/arras-energy/gridlabd-library) | [![validate](https://github.com/arras-energy/gridlabd-library/actions/workflows/master.yml/badge.svg)](https://github.com/arras-energy/gridlabd-library/actions/workflows/master.yml) [![validate](https://github.com/arras-energy/gridlabd-library/actions/workflows/develop.yml/badge.svg)](https://github.com/arras-energy/gridlabd-library/actions/workflows/develop.yml)
| [Models](https://github.com/arras-energy/gridlabd-models) | [![validate](https://github.com/arras-energy/gridlabd-models/actions/workflows/validate.yml/badge.svg)](https://github.com/arras-energy/gridlabd-models/actions/workflows/validate.yml)
| [Benchmarks](https://github.com/arras-energy/gridlabd-benchmarks) | Manual test (see [README.md](https://github.com/arras-energy/gridlabd-benchmarks/blob/main/README.md))
| [Examples](https://github.com/arras-energy/gridlabd-examples) | Manual test (see [README.md](https://github.com/arras-energy/gridlabd-examples/blob/master/README.md))

| [Tutorials](https://github.com/gridlabd-tutorials) | Topic | Status |
| :---: | :--- | :---: |
| [Lesson 1](https://github.com/gridlabd-tutorials/lesson-1) | Create a GitHub project, download a reference model, solve powerflow, and plot a voltage profile. | [![Simulation](https://github.com/gridlabd-tutorials/lesson-1/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-1/actions/workflows/main.yml)
| [Lesson 2](https://github.com/gridlabd-tutorials/lesson-2) | Modify, create, and delete static loads. | [![Simulation](https://github.com/gridlabd-tutorials/lesson-2/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-2/actions/workflows/main.yml)
| [Lesson 3](https://github.com/gridlabd-tutorials/lesson-3) | Create distributed generation resources such as rooftop solar, wind, and backup generators. | [![Simulation](https://github.com/gridlabd-tutorials/lesson-3/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-3/actions/workflows/main.yml)
| [Lesson 4](https://github.com/gridlabd-tutorials/lesson-4) | Create energy storage devices such as residential wall-mount batteries and community energy storage | [![Simulation](https://github.com/gridlabd-tutorials/lesson-4/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-4/actions/workflows/main.yml)
| [Lesson 5](https://github.com/gridlabd-tutorials/lesson-5) | Running simulations over time | [![Simulation](https://github.com/gridlabd-tutorials/lesson-5/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-5/actions/workflows/main.yml)
| [Lesson 6](https://github.com/gridlabd-tutorials/lesson-6) | Managing weather | [![Simulation](https://github.com/gridlabd-tutorials/lesson-6/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-6/actions/workflows/main.yml)
| [Lesson 7](https://github.com/gridlabd-tutorials/lesson-7) | Adding quasi-static loads | [![Simulation](https://github.com/gridlabd-tutorials/lesson-7/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-7/actions/workflows/main.yml)
| [Lesson 8](https://github.com/gridlabd-tutorials/lesson-8) | Exporting data | [![Simulation](https://github.com/gridlabd-tutorials/lesson-8/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-8/actions/workflows/main.yml)
| [Lesson 9](https://github.com/gridlabd-tutorials/lesson-9) | Importing data | [![Simulation](https://github.com/gridlabd-tutorials/lesson-9/actions/workflows/main.yml/badge.svg)](https://github.com/gridlabd-tutorials/lesson-9/actions/workflows/main.yml)

