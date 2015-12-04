Brainhack Report
========================

Craddock and Clark: 3dLFCD and 3dDegreeCentrality

To compile this paper you will need a to have a distribution of LaTex that includes bibtex and pdflatex tools as well as Pandoc installed on your local computer. If you have a PC, I am not sure how you install latex.

On Mac:
The installation of LaTex can be easily achieved on a Mac using the [mactex package](https://tug.org/mactex/). 

For Ubuntu:
    
	sudo apt-get install texlive-full

For Redhat/CentOS/Fedora (I believe that this will work):
	
	sudo yum install texlive

The Brainhack Report is written in Markdown and then converted into LaTex using a Brainhack report template. To perform this step you will need to have Pandoc installed. This can be accomplished on a variety of operating systems using instructions from the [Installing Pandoc web page](http://pandoc.org/installing.html).

If you have make installed you can compile the paper using:
    
    make

Otherwise you will need to run the commands:
    
	pandoc -s -S -N --template brainhack-report-template.tex brainhack-report.md -o brainhack-report-formatted.tex
	pdflatex brainhack-report-formatted.tex
	bibtex brainhack-report-formatted
	pdflatex brainhack-report-formatted.tex
	pdflatex brainhack-report-formatted.tex

The multiple runs makes sure that all references are resolved. If you do not 
change the bib file you will not need to rerun the bibtex command.

Fairly accurate word counts, ignoring latex commands, can be calculated using:

    	texcount brainhack-report-formatted.tex

