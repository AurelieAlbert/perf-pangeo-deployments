# Performance tests on various pangeo deployments

## Pangeo deployments

  - personnal computer
  - [IGE](http://www.ige-grenoble.fr/) cluster cal1
  - [GRICAD](https://gricad-doc.univ-grenoble-alpes.fr/) intensive computing cluster [dahu](https://gricad-doc.univ-grenoble-alpes.fr/hpc/description/)
  - [CNES](https://cnes.fr/fr/) intensive computing cluster hal
  - [CINES](https://www.cines.fr/) supercomputer [occigen](https://www.cines.fr/calcul/materiels/occigen/)
  - [IDRIS](http://www.idris.fr/info/missions.html) supercomputer [jean-zay](http://www.idris.fr/jean-zay/)
  - [PANGEO](https://pangeo.io/index.html) [cloud](https://pangeo.io/deployments.html)

## The data

The exact same dataset has been uploaded in every PANGEO deployment : the sea surface height in the North Atlantic 
region simulated by NEMO between 2009, July the 1st and 2010, October the 1st, hereafter eNATL60-BLBT02-SSH. 

The dataset is a zarr archive, is 621Go big and contains 17 641 individual files.

## The tests

The opening of the zarr (perf 1), the virtual computation of the time-mean over the whole period (perf 2) and the actual computation (perf 3) will be timed.

To garantee the robustness of the test, the exact same python configuration will be deployed, it is described in the [conda environment.yml]() file.

For the machine with different computation nodes, several tests will be made.

## Results

- Perf 1 : Opening the 621Go zarr archive

<table>
    <thead>
        <tr>
            <th>Machine</th>
            <th>File System</th>
            <th>Timing</th>
        </tr>
    </thead>
    <tbody>
        <tr>
             <td>Personnal Computer</td>
             <td></td>
             <td></td>
        </tr>
        <tr>
            <td>Cluster cal1</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Cluster dahu GRICAD</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC hal CNES</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC occigen CINES</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC jean-zay IDRIS</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>PANGEO cloud</td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>

- Perf 2 : Dask delayed operation of temporal mean

<table>
    <thead>
        <tr>
            <th>Machine</th>
            <th>Node type</th>
            <th>Nb workers</th>
            <th>Total memory</th>
            <th>Timing</th>
        </tr>
    </thead>
    <tbody>
        <tr>
             <td>Personnal Computer</td>
             <td></td>
             <td></td>
             <td></td>
             <td></td>
        </tr>
        <tr>
            <td>Cluster cal1</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Cluster dahu GRICAD</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC hal CNES</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC occigen CINES</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC jean-zay IDRIS</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>PANGEO cloud</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>

- Perf 3 : Actual computation of temporal mean

<table>
    <thead>
        <tr>
            <th>Machine</th>
            <th>Node type</th>
            <th>Nb workers</th>
            <th>Total memory</th>
            <th>Timing</th>
        </tr>
    </thead>
    <tbody>
        <tr>
             <td>Personnal Computer</td>
             <td></td>
             <td></td>
             <td></td>
             <td></td>
        </tr>
        <tr>
            <td>Cluster cal1</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Cluster dahu GRICAD</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC hal CNES</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC occigen CINES</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>HPC jean-zay IDRIS</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>PANGEO cloud</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>
