# anisotime
![version][version-image]
[ ![release][release-image] ][release]
[ ![aLicense][alicense-image] ][alicense]
[ ![oLicense][olicense-image] ][olicense]
[ ![Java8][Java8-image] ][Java8] 


anisotime is a utility package mainly to compute travel time in a laterally homogeneous, transversely isotropic (TI), spherically symmetric medium.

# INSTALLATION

### For macOS or Linux users:
 
Please download [this][anisosh] and run as below:

    //When you want to download the file under /path/to 
    $ anisotime=/path/to/anisotime
    $ wget -O $anisotime https://bit.ly/2XI9KT7 || curl -L -o $anisotime https://bit.ly/2XI9KT7
    $ chmod +x $anisotime
    $ $anisotime (OPTIONS)

### For Windows users:

Please [check](https://bit.ly/2r9KA3J) if you have Java Runtime Environment.
Batch file for Windows can be downloaded [here][anisobatch].

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
anisotime
```

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
anisotime -help
```

### Catalog creation
If you want to create a database of raypath set that shortens the time for travel time computation,
``` bash
anisotime -mod prem
```
it creates a catalog and the catalog is used from the next use.  
If you want to specify a catalog for the raypath computation:
``` bash
anisotime -rc /path/to/catalog -deg 60 -ph S
```

### Record section
If you want to create P and S wave record sections for an epicentral distance range ```start``` to ```end``` with interval ```interval``` and let the results in ```/path/to/out``` (must not exist before the launch),
```bash
anisotime -rs start,end,interval -ph P,S -mod prem -o /path/to/out
```
Without ```-o```, it shows the result in the standard output.

