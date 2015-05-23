[![Build Status](https://buildhive.cloudbees.com/job/centic9/job/poi-mail-merge/badge/icon)](https://buildhive.cloudbees.com/job/centic9/job/poi-mail-merge/) 

This is a small application which allows to repeatedely replace markers in a Microsoft Word document with items taken from a CSV/Microsoft Excel file. 

I started this project as I was quite disappointed with the functionality that LibreOffice offers, I especially wanted something that is repeatable/automateable
and does not produce spurious strange results and needs re-configuration each time the mail-merge needs to be (re-)run.

## How it works

you provide a word-document which contains template-markers for things that should be replaced, e.g. "<first-name> <last-name>".

The first sheet of the Excel file is read and needs to contain a header row which is used to match the template-names used in 
the Word-template.

The result is a single merged Word-document which contains a copy of the template for each line in the Excel file.

## Use it

### Grab and compile it

    git clone git://github.com/centic9/poi-mail-merge
	cd poi-mail-merge
	./gradlew installDist

### Use it

	./run.sh <word-template> <excel-file>

## Change it

### Create Eclipse project files

	./gradlew eclipse

### Build it and run tests

	cd poi-mail-merge
	./gradlew check jacocoTestReport

#### Licensing
* poi-mail-merge is licensed under the [BSD 2-Clause License].
* A few pieces are imported from other sources, the source-files contain the necessary license pieces/references.

[BSD 2-Clause License]: http://www.opensource.org/licenses/bsd-license.php
