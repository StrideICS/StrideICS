# MTMT templates building tool

This tool allows to build a Microsoft Threat Modeling Tool (MTMT) template from a TOML file.
STRIDE threats will automatically be inserted in the generated template by searching CVE databases.

## Prerequisites

This tool is meant to run using Python in version 3.9.
Install requirements from `requirements.txt` file: `pip install -r requirements.txt`.


## Building the MTMT template

The tool requires in input a TOML configuration file to generate a templates .tb7 for MTMT. To run the code :
In a terminal : `python3.9 tomltoTemplate.pyc <path to the toml file> <(optional)NVD api key>`

An example of TOML configuration file is provided in *DB_ICS.toml* and its output in *DB_ICS_open_2_1.tb7*.
The TOML file must respect the following structure :
```TOML

[project]
title = ""
version = ""
author = ""
id = "<uuid4>"

[cveGathering]
	[cveGathering."Name"]
	ID = '<uuid4>'
	cpe = "<cpe:2.3>"
	period = ["YYYY-MM-DD","YYYY-MM-DD"]
	severity = ["CRITICAL", "HIGH", "MEDIUM", "LOW"]

[GenericElements]
    [GenericElements."NAME1"]
    ID = "<uuid4>"
	Description = ""
	ParentElement = ""
	Image = "<base64>"
	Hidden = "false"
	Representation = ""
	StrokeThickness = "0"
	ImageLocation = ""
	StencilConstraints = [{SelectedStencilType = "Any", SelectedStencilConnection = "Any"}]
    #optional
	Attributes."Attr1" = ["Value1", "Value2"]
	Attributes."Attr2" = ["Value1", "Value2", "Value3"]

[StandardElements]
    [StandardElements."NAME1"]
    ID = "<uuid4>"
	Description = ""
	ParentElement = ""
	Image = "<base64>"
	Hidden = "false"
	Representation = ""
	StrokeThickness = "0"
	ImageLocation = ""
	StencilConstraints = [{SelectedStencilType = "Any", SelectedStencilConnection = "Any"}]
    #optional
	Attributes."Attr1" = ["Value1", "Value2"]
	Attributes."Attr2" = ["Value1", "Value2", "Value3"]

[ThreatCategories]
	[ThreatCategories."NAME"]
	Id = "" 
	ShortDescription = ""
	LongDescription = ""

[ThreatTypes]
	[ThreatTypes."NAME"]
	GenerationFilters.Include = ""
	GenerationFilters.Exclude = ""
	Id = ""
	Category = ""
	Description = ""
```