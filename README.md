# anisotime


![version](https://img.shields.io/badge/version-1.3.7-yellow.svg)
![release](https://img.shields.io/badge/release-Eulmore-yellow.svg)
![aLicense](https://img.shields.io/badge/license-GPL--3-blue.svg?style=flat)
![Java8](https://img.shields.io/badge/dependencies-JRE%208-brightgreen.svg)

ANISOtime is a utility package mainly to compute travel time in a laterally homogeneous,
transversely isotropic (TI), spherically symmetric medium.


Please [check](https://java.com/ja/download/installed8.jsp) if you have Java Runtime Environment (8+). 
It is required to run ANISOtime.

# INSTALLATION

For users [Windows](#for-windows-users), [macOS and Linux](#for-macos-or-linux-users).

### For macOS or Linux users:
 
Please run as below:

    //When you want to download the file under /path/to 
    $ anisotime=/path/to/anisotime
    $ wget -q -O $anisotime https://bit.ly/2XI9KT7 || curl -sL -o $anisotime https://bit.ly/2XI9KT7
    $ chmod +x $anisotime
    $ $anisotime (OPTIONS)

### For Windows users:

Batch file for Windows can be downloaded [here](https://bit.ly/2QUnqJr).

    // You can easily get this path when you drag and drop the file on the prompt.
    $ "/path/of/anisotime.bat" (options)

# Velocity model
*anisotime* includes the following well-known velocity structures:  
[PREM](http://ds.iris.edu/ds/products/emc-prem/)(prem)  
[AK135](http://ds.iris.edu/ds/products/emc-ak135-f/)(ak135)  
[Isotropic PREM](http://www.sciencedirect.com/science/article/pii/0031920181900467)(iprem)

Names in the parenthesis are to be used as a model name in CLI.

Hereinafter, ```/path/to/Kibrary/bin``` is assumed to be in PATH.

# USAGE
## GUI
If you want to use *anisotime* in its GUI mode, execute *anisotime* as below:
``` bash
//GUI mode runs when you activate ANISOtime without any options.
 $ anisotime //Linux macOS
```

```windows
 $ anisotime.bat //Windows
```

Hereinafter, Windows users might as well to replace ```anisotime``` as ```anisotime.bat``` as above.


## CLI
When you add arguments in the command of the above execution for the GUI mode,
it works as CLI.

### Arguments
* -dec <arg> Number of decimal places for output.
* -deg <arg> Epicentral distance &Delta; [deg].
* -h <arg>   Depth of source [km] (default:0)
* -mod <arg> Structure (default:prem)
* -help Prints the usage. <u>This option has the highest priority.</u>
* -ph, --phase <arg> Seismic phases (default:P,PCP,PKiKP,S,ScS,SKiKS)
* -p <arg> Ray parameter
* -v, --version Shows information of the tool. <u>This option has the 2nd highest priority.</u>
* -SH Computes travel time for SH (default:SH)
* -SV Computes travel time for SV (default:SH)
* -dD <arg> Parameter for a catalog creation (dΔ).
* -dR <arg> Integral interval [km] (default:10.0)
* -eps  output path figure
* -o <arg> Directory for a record section. It must not exist before the launch.
* --delta  show only epicentral distances
* --rayp   show only ray parameters
* --time     show only travel times
* -rc, --read-catalog <arg> Path of a catalog for which travel times are computed.
* -rs, --record-section <arg>   start,end(,interval) [deg] Computes a table of a record section for the range.

  

For instance, if you want to see the usage, you can execute as below:
``` bash
 $ anisotime -help
```

### Examples

```$``` is a prompt. ```anisotime``` should be in PATH, otherwise it should be replaced as ```/path/to/anisotime```
```
 $ anisotime -h 10 -mod prem -deg 60 
# this command returns values for raypaths with epicentral distance of 60 deg from an event (depth 10 km) under the anisotropic PREM structure.
```

```
 $ anisotime -h 10 -mod prem -deg 10 -ph P 
# this command returns values for P phase with epicentral distance of 10 deg from an event (depth 10 km) under the anisotropic PREM structure.
```

```
 $ anisotime -h 30 -mod prem -deg 30 -ph S -SH 
# this command returns values for S phase raypaths with epicentral distance of 30 deg from an event (depth 30 km) under the anisotropic PREM structure. 
# When -SH option is set, returning values are of SH waves.
 $ anisotime -h 30 -mod prem -deg 30 -ph S -SV 
# When -SV option is set, returning values are of SV waves.
```

```
 $ anisotime -h 30 -mod iprem -deg 100 -ph Pdiff 
# this command returns values for Pdiff phase with epicentral distance of 100 deg from an event (depth 30 km) under the isotropic PREM structure.  
```

```
 $ anisotime -h 30 -mod iprem -deg 30 -ph P,S 
# this command returns values for P and S phase with epicentral distance of 30 deg from an event (depth 30 km) under the isotropic PREM structure.
```

```
 $ anisotime -h 30 -mod iprem -ph ScS -rs 30,50,1 -o scs.rcs 
# this command creates a file scs.rcs which includes record section values for ScS phase with epicentral distances of 30 to 50 deg with interval of 1 deg from an event (depth 30 km) under the isotropic PREM structure.
```

```
 $ anisotime -h 30 -mod iprem -deg 30 -ph P,S -eps -o out 
# this command creates raypath figures under the folder out for P and S phases with epicentral distance of 30 deg from an event (depth 30 km) under the isotropic PREM structure.
```
  




### Catalog creation
If you want to create a database of raypath set that shortens the time for travel time computation,
``` bash
 $ anisotime -mod prem
```
it creates a catalog and the catalog is used from the next use.  
If you want to specify a catalog for the raypath computation:
``` bash
 $ anisotime -rc /path/to/catalog -deg 60 -ph S
```

### Record section
If you want to create P and S wave record sections for an epicentral distance range ```start``` to ```end``` with interval ```interval``` and let the results in ```/path/to/out``` (must not exist before the launch),
```bash
 $ anisotime -rs start,end,interval -ph P,S -mod prem -o /path/to/out
```
Without ```-o```, it shows the result in the standard output.

## Copyright and Licence
ANISOtime Copyright © 2020 Kensuke Konishi, Anselme Bourgeaud, Kenji Kawai and Robert J. Geller   
Licensed under [GNU General Public License v3](https://www.gnu.org/licenses/gpl-3.0.html)  
Last updated Jul 3, 2020
 
