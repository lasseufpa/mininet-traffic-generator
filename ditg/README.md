# MGEN Traffic Generator 

## Install MGEN 5.1.1 traffic generator
### Install libpcap library
```
sudo apt install libpcap-dev
```

### Clone MGEN repository
```bash
git clone https://github.com/USNavalResearchLaboratory/mgen.git
```

### Execute the following commands

```bash
cd mgen
git submodule update --init
cd makefiles
make -f Makefile.linux
```

## Traffic generator usage
### Flags:
- `--topo-filepath`: Path to network topology (gml file) to be used in the simulations.
- `--id`: Experiment identifier defined by an integer number.

### Generate traffic:
In order to generate traffic you should run the below command, considering an identifier equal to 1 and a toy topology `toy_topology.gml`:
```bash
sudo mn -c && sudo $(which python) generate_traffic.py --id 1 --topo-filepath topology/toy_topology.gml
``` 

### Generate deep learning data
In order to convert the raw traffic data generated with iperf to tensorflow dataset, you should run the command below:
```bash
python3 generate_data.py --exp-path [path-to-input-data] --output-dir [path-to-output-data]
``` 