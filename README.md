# MTMT templates building tool

This tool allows to build a Microsoft Threat Modeling Tool (MTMT) template from a TOML file.
STRIDE threats will automatically be inserted in the generated template by searching CVE databases.
Anonymous Github tool does not support cloning repository, please download `RELEASE_FOR_DOWNLOAD.tar.gz` for easy code access.

## Prerequisites

This tool is meant to run using Python in version 3.9.
Install requirements from `requirements.txt` file: `pip install -r requirements.txt`.

## Building the MTMT template

The tool requires in input a TOML configuration file to generate a templates .tb7 for MTMT. To run the code :
1. In a terminal : `python3.9 insertion_threat.pyc`
2. Enter the path to the TOML configuration file
3. Open the new template with MTMT and save it

An example of TOML configuration file is provided in *DB_ICS_open.toml* and its output in *DB_ICS_open.tb7*.
The TOML file must respect the following structure :

```TOML
[Create_Project]
title = ""
version = ""
auteur = ""

[Stencil_search_CVE]
	[Stencil_search_CVE.1]
	name = ""
	period = ["", "", ""]
	severity = ["", ""]

[stencils]
    [stencils.X]
    name = ""
    description = ""
    img_loc = ""
    Repre_stencil = ""
        [stencils.X.proprietiesY]
        name = ""
        values1 = ""

[derived_stencils]
    [derived_stencils.X]
    stencil_base = ""
    name = ""
    description = ""
    img_loc = ""

[Threat_Categories]
    [Threat_Categories.X]
    name = ""
    description = ""

[Basic_Type_Threat]
    [Basic_Type_Threat.X]
    Parent = ""
    name = ""
    include = ""
    exclude = ""
    Description = ""
```
