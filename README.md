# Generate traffic using D-ITG

## Install D-ITG traffic generator 2.8.1
```
sudo apt install d-itg
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
Other topologies are availabe, such:
- `5G_crosshaul_51.gml`
- `germany_50.gml`
- `HPASSION_128.gml`
- `PASSION_128.gml`
- `nsfnet_14.gml`

You can also custom your own topology, using a .gml file, to simulate traffic.

### Generate deep learning data
- `--exp-path`: It is the path to the raw data.
- `--output-dir`: It is the path to the output data in tensorflow format.
In order to convert the raw traffic data generated with DITG to tensorflow dataset, you should run the command below:
```bash
python3 generate_data.py --exp-path [path-to-input-data] --output-dir [path-to-output-data]
``` 