# Generate traffic using D-ITG

## Installing D-ITG traffic generator 2.8.1
```bash
sudo apt install d-itg
```

## Deploying a ONOS controller in a docker container
To deplay the ONOS controller to further uses by the Mininet emulator, you should run the following commands in the same directory of `compose.yml` file:
```bash
sudo docker compose up -d
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
Other topologies are availabe, such as:
- `5G_crosshaul_51.gml`
- `germany_50.gml`
- `HPASSION_128.gml`
- `PASSION_128.gml`
- `nsfnet_14.gml`

You can also custom your own topology, using a .gml file, to simulate traffic.

### Generate deep learning data (input-output examples)
- `--exp-path`: It is the path to the raw data.
- `--output-dir`: It is the path to the output data in tensorflow format.

In order to convert the raw traffic data generated with DITG to tensorflow dataset, you should run the command below:
```bash
python3 generate_data.py --exp-path [path-to-input-data] --output-dir [path-to-output-data]
``` 

## Credits
If you benefit from this work, please cite on your publications using:
```
@misc{modesto2025,
      title={Towards a Robust Transport Network With Self-adaptive Network Digital Twin}, 
      author={Cláudio Modesto and João Borges and Cleverson Nahum and Lucas Matni and Cristiano Bonato Both and Kleber Cardoso and Glauco Gonçalves and Ilan Correa and Silvia Lins and Andrey Silva and Aldebaro Klautau},
      year={2025},
      eprint={2507.20971},
      archivePrefix={arXiv},
      primaryClass={cs.NI},
      url={https://arxiv.org/abs/2507.20971}, 
}
```