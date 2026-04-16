---
description: Use these instructions when asked about melconv or when converting monophonic melody files into another is appropriate
# applyTo: 'Use these instructions when asked about melconv or when converting monophonic melody files into another is appropriate' # when provided, instructions will automatically be added to the request context when the pattern matches an attached file
---

melconv
Introduction
melconv is a command-line tool for converting monophonic melody files into another. The main structure behind is star-shaped: Files are read and converted into a internal format and afterwards exported in the desired output format (cf. Fig. 1: General schema.). Not all formats possess the same expressivity, so some conversion can either not be carried out or only with a loss of information.

../../\_images/melconv_schema.jpg
Fig. 1: General schema.

melconv input formats

SV projects files (Jazzomat type)

MCSV1 format

MCSV2 format (since melconv v1.1.4, MeloSpyGUI v1.2, MeloSpySuite v1.4)

SQLITE/WJazzD format

EsAC (old and extended format)

MIDI

Tony generated note tracks as CSV files

melconv output formats

MCSV1 format

MCSV2 format

SQLITE/WJazzD format

MIDI format

Notes (simple onset/pitch format as used by Temperley)

Lilypond (since melconv v1.1.4, MeloSpyGUI v1.2, MeloSpySuite v1.4)

Usage
Here is the basic call to melconv:

melconv [-h] [--version] [-d DIR] [-o OUTDIR] [-c CONFIG]
[-f {mcsv1,meter,notes,midi,krn}] [-i INPUT]
[--inputformat INPUTFORMAT] [-t TRANSPOSE] [--dbtype DBTYPE]
[--dbpath DBPATH] [--dbuser DBUSER]
[--dbpwd DBPWD] [--dbrebuild [DBREBUILD]]
[positional]
If used without configiration file, melconv only converts one file at a time. For mass conversion, the use of the configuation file is strongly advised.

Options and arguments
-h, --help
Show a help message and exits.

--version
Shows program’s version number and exit.

-d <DIR>, --dir <DIR>
Use <DIR> as working directory for reading the project files. Default is the current directory.

-o <OUTDIR>, --outdir <OUTDIR>
Write files or database to <OUTDIR>. Default is the current directory.

-c <CONFIG>, --config <CONFIG>
Use the configuration file <CONFIG>, see below. The arguments <DIR> and <OUTDIR> override the settings in the config file. but the positional argument is ignored while using the config file.

-f {mcsv1,esac,meter,notes,midi,database}, --format {mcsv1,esac,meter,notes,midi,database}
This options specifies the desired output format. Ignored in presence of a configuration file. Defaults to mscv1 format. Has precedence over according value in configuration file. Case insensitive.

-i INPUT, --input INPUT
Absolute or relative path to the file to be converted. Ignored in presence of a configuration file.

--inputformat INPUTFORMAT
Force to use INPUTFORMAT as format of the input files instead of guessing from file extension.

-t TRANSPOSE, --transpose TRANSPOSE
Transpose output by TRANSPOSE semitones. Include sign for upward resp. downward transposition. Has precedence over according value in configuration file.

--dbtype DBTYPE
If output format is database, one must specify the type of database here. Currently only SQLITE3 is supported (also default). Has precedence over according value in configuration file.

--dbpath DBPATH
Absolute or relative path to the output database. Has precedence over according value in configuration file.

--dbuser DBUSER
If credentials are needed for database access, here the user name can be specified. Has precedence over according value in configuration file.

--dbpwd DBPWD
If credentials are needed for database access, here the password can be specified. Has precedence over according value in configuration file.

--dbrebuild [DBREBUILD]
If output format is database, it can be specified with this option whether the database should be completely rebuild (ATTENTION: deletes all previous contents). If the database is not to be rebuilt, the new entities are inserted without any further checking, which might lead to unexpected results. Any non-empty value will do it (might change in the future.) Has precedence over according value in configuration file.

positional arguments
The file name of the output. Ignored in presence of a configuration file.

Configuration file
Currently, converting of more than one file is only possible using the configuration file. Moreover, the output format is global, hence, all specified input files will be converted into the same output format. For certain output and input formats some extra parameters are needed (or at least desirable), these can only be specified using the configuration file, see Input and output parameters for details. The configuration files use YAML syntax. Here is an example:

---

dir: /My/Data/
outdir: /My/Data/DB

flexq:
oddDivisionPenalty: 1.2
mismatchPenalty: 1.1
distPenalty: 7.3
spreadPenalty: 10.2
optimize: True
rhythmThreshold: 0.05
scaleFactor: .87
tolerance: .015

output:
format: midi
tempo: auto
transpose: -12
quantize: True
quantize_duration: True

bundles:

- file: 'Miles\*\_PREFINAL.sv'
- file: 'J*Impressions*\_PREFINAL.sv'
- query:
  conditions:
  solo_info: - performer: 'Miles%' - title: '~Impressions%' - performer: '~John%'
  display:
  transcription_info: filename_sv
  type: sv

srcdatabase:
type: sqlite3
path: esac.db
use: False
password: None
content-type: sv
version: 2

sinkdatabase:
type: sqlite3
path: solo.db
rebuild: True
password: None
release: 1.2
Explanation
The dir and outdir parameters have the same meaning as the corresponding commandline parameters. The output section contains parameter setting for the output. format has the same meaning as the commandline parameter. Possible values are mcsv1, mcsv2, esac, meter, notes, midi, database. Except transpose the remaining output parameters are format specific, see Output parameters for more information.

Under the section bundles an arbitrary long list of input files can be specified. There are two basic possibilities: Reading from files or from a database. Bundle starting with the keyword file are read from files as specified by the following value (use of wildcards is permitted), and bundles starting with query are read from a source database as specified in the corresponding section srcdatabase. See Query block syntax for more information how to write database queries.

The block for srcdatabase is used to read from a database. In this case, the flag use must be set to True , otherwise the section and any query-bundles will be ignored. If a source database is to be used, all file sets in the files sections are ignored and only the query sections are considered. Likewise, if no srouce database is used (parameter use is set to False), all query entries are ignored. The query syntax is explained below.

The block for sinkdatabase is used if data is to be written into a database. The fields are the same as the corresponding commandline parameters. If database is the output format, but not sink database is specified, melconv will fail.

The block for flexq is used by the metrical annotation algorithm (Flex-Q) for reading SVFiles and can mostly be omitted, in which case reasonable default values will be used. However, sometimes different settings might help in achieving a successful annotation for critical cases.

Query block syntax
A database query block consists of three fields: conditions, display and type. Basically there are currently two types of data, EsAC and Jazzomat (SV) tunes. They differ in the metadata provided for a melody (cf. SQLITE3 database formats). Hence, the possible type specifications in the type field are sv and esac. The display specifies the name to be used for the melody object, and must refer to a valid entry in the database. The syntax is <METADATA-TABLE>: <COLUMN-NAME>. For example, transcription_info is a metadata table name in the SV-database format, which has a column named filename_sv, which is the file name of the source SV project file for a SV melody object.

A similar logic holds for the conditions field. It must have a valid table name as primary key and a sub-ordinate list of conditions on specific column names in the format <COLUMN-NAME>: [~]<CONDITION>. If more than one primary key is defined, only the last one will be used.

The conditions are translated to SQL LIKE statements, where the SQL-wildcard % can be used (‘\*’ will also work). These LIKE-statements are conjuncted to a single WHERE-clause for a SELECT query which will be executed on the database to retrieve a result set of melody objects. Negations are indicated by preceding the condition with a ~-Symbol, which will get translated to a NOT LIKE clause.

Example:

- query:
  conditions:
  solo_info: - performer: 'Miles%' - performer: 'John%' - title: '~Impressions%'
  display:
  transcription_info: filename_sv
  type: sv
  This query will retrieve all melody objects where the performer field in the table solo_info is either starting with “Miles” or with “John”, but all songs which title starts with “Impressions” will be excluded. The type is accordingly set to sv, if it was esac, the tables solo_info and transcription_info would be empty and the query would return an empty a result set. Finally, for display purposes (e.g., in a feature results file), filename_sv from table transcription_info is used in this example for display purposes, but every other valid, non-empty fields could have been used as well.

Note

If there is more than one query sections, which will result in an overlapping set of melody/display name combinations, i.e. with doublets, the command-line tools will only fetch each unique melody/display name combination once.

Input and output parameters
Since v1.1.4 of melconv (MeloSpySuite 1.4), the specification of input and output parameters was modified and extended.

Input parameters
MSCV1 reading
Example:

mcsv_reader:
requantize: False
max_div: 6
For reading MCSV1 files two parameters are now available, requantize is a boolean parameter which will trigger a requantization with parameter max_div, the maximal allowed division of beats.

Output parameters
MIDI wrinting
Example:

output:
format: midi
tempo: auto
transpose: -12
quantize: True
quantize_duration: True
ticks_per_beat: 192
volume: log_range
tempo indicates the tempo (in BPM) to be used for writing the MIDI files. If set to auto, the original tempo of the input files will be retained (if present, else a default tempo of 120 BMP is used).

quantize is a boolean value indicating if the onset should be quantized according to the metrical information contained in the input file.

quantize_duration is doing the same for duration values. If set to True, durations are calculated as inter-onset intervals on the base of metrical information. If set to False, the original duration are used.

ticks_per_beat enforces the specicife ticks per beeat value in the output

volume is an partly experimental feature that applies only to solos from the Weimar Jazz Database for non constant values. This parameter specfies the mapping of loudness values (if available) to MIDI velocity. Available options are: log_range, log_fixed, linear or a integer value between 0 and 127. In the last case (default with value 100), a constant velocity of the specified value will be used.

Lilypond writing
Example:

output:
format: lilypond
tempo: auto
transpose: 12
upbeat: True
clef: bass
For conveting to Lilypond files, four parameters are available.

tempo will set the tempo indication to the specified numeric value. If set to auto (default), the tempo of the original source will be used (if available).

transpose allows transposing the whole score the specified amount of semitones.

upbeat (True or False) will enforce using upbeats instead of full bars with pauses (does not work with WJazzD solos).

The value of clef will be used in the output file (accoridngt to Lilypond syntax), if set to auto, the clef will be determined automatically.
