# ASSuME
“This study project has been carried out in the Bioinformatics Minor of Academie voor de Technologie van Gezondheid en Milieu at Avans Hogeschool under the supervision of Dr. ir. Miaomiao Zhou and Dr. Kees Rodenburg. “ 

Amplicon Sequencing Snp MappEr

Usage

Usage: Python ASSuME.py -gene [GENE] [Options]

	Options:
	-o: output file (default: None).
	-pr: print the output to the screen (True/False)(default: True).
	-flanking: Amount of extra flanking DNA (3 and 5-prime). Set to 0 if you
         	 just want the gene. 10000 will include most enhancer and promotor regions
	(default: 10000).
 	-ampl_min: minimal amplicon length (default: 500).
 	-ampl_max: maximal amplicon length. (default: 10000).
  	-ampl_n: approx. amount of generated amplicons (default: 90).
  	-tm_min: minimal primer melting temperature (default: 59.0).
  	-tm_opt: optimal primer melting temperature (default: 62.0).
	-tm_max: maximal primer melting temperature (default: 64.0).
	-h, --help: show help

	Examples:

	Python ASSuME.py -gene 7157 -o TP53_output.txt -pr False
		Runs ASSuME on the TP53 gene. Generates the output as the          
		‘TP53_output.txt’ file. Doesn’t display output to the terminal.

	Python ASSuME.py -gene 7157 -ampl_n 20 -tm_min 65 -tm_opt 68 -tm_max 70
		Runs ASSuME on the TP53 gene. Displays the output to the 
		terminal. Designs ~ 20 primersets with a minimal/optimal/maximal 
		tm of 65/68/20 ˚C.

Installation

PRIMER3 INSTALLATION

Primer3 needs to be installed. More detailed install instructions are given in the Primer 3 manual.
(http://primer3.sourceforge.net/primer3_manual.htm)

LINUX

Type the following commands in the terminal. Make sure it is installed as binary.

`sudo apt-get install -y build-essential g++ cmake git-all`
`git clone https://github.com/primer3-org/primer3.git primer3`
`cd primer3/src`
`make`

MAC OSX

Installation via homebrew is recommended (install homebrew if you have not done
so already). Manual installation is also possible: see Primer3 documentation. 
Make sure it is installed as binary (homebrew does this automatically).

`brew install brewsci/science/primer3`

Move ‘Primer3/primer3-1.1.4-OSX/primer3_config’ to: /usr/local/Cellar/primer3/2.4.0/bin/primer3_config/

PYTHON 

ASSuME is based on Python3.6+ and will not run on legacy Python 2.7. It relies on the following packages to work:
-	numpy
-	pandas
-	sqlalchemy
-	argparse
-	mygene
These packages can all be installed with pip3 e.g.: pip3 install <module> 
