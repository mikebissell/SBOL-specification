# SBOL-specification

This repository contains the master specification document for the SBOL data model, formatted in LaTeX.  The workflow for updating the specification is to clone, edit, and submit a pull request on the master.

Members of the SBOL Development Community may use the issue tracker to flag problems with the existing specification and review ongoing issues under consideration.


# Building the PDF from LateX

To build, run these commands and check the output for errors. If there are errors, resolve them and re-run the failed build step before proceeding.

    pdflatex sbol2
    bibtex sbol2
    pdflatex sbol2
    pdflatex sbol2

Note that pdflatex is run several times. Each successive pass mows down unresolved references from the previous pass. For development purposes, you may just need to run it once unless you're editing features that only appear after later build steps.

The git status command will show you which intermediate build products and logs you need to delete for a clean build.


# LaTeX installation notes

Installing LaTeX on your system is beyond the scope of this README, however we will collect some tips here, in the interest of fostering collaboration.


# MacTex installation notes

Here is how one community member managed to install MacTex and BibTex on OS X 10.10.5 Yosemite in August 2016. This recipe was found on StackOverflow. Not all of these commands may be strictly necessary to build the SBOL2 pdf at this time.

    # First install homebrew from http://brew.sh then...
    brew update
    brew upgrade
    brew tap caskroom/cask
    brew install brew-cask
    brew cask install mactex
    brew cask install bibtex
    brew cask install bibdesk
    brew cask install texshop
    brew cask install mendeley-desktop
    sudo chown -R $USER  /usr/local/texlive
    tlmgr update --self
    tlmgr update --all
    defaults write TeXShop NSUserKeyEquivalents -dict-add "Typeset" "@t"
    defaults write TeXShop "BibTeXengine" -string "biber"
    defaults write TeXShop "Encoding"  -string  "IsoLatin"
    defaults write edu.ucsd.cs.mmccrack.bibdesk "Cite Key Format" -string %y%u0"
    defaults write edu.ucsd.cs.mmccrack.bibdesk BDSKLocalFileFormatKey -string Cite Key}%n0%e"
    defaults write edu.ucsd.cs.mmccrack.bibdesk "Path to the papers folder" ing "Biblio"
    defaults write edu.ucsd.cs.mmccrack.bibdesk "Cite String" -string "citep"
    defaults write edu.ucsd.cs.mmccrack.bibdesk "Cite Key Autogenerate" -int 1
    defaults write edu.ucsd.cs.mmccrack.bibdesk "Cite Key Format Preset" -int 0
    defaults write edu.ucsd.cs.mmccrack.bibdesk "Cite Prepend Tilde" -int 1
    defaults write edu.ucsd.cs.mmccrack.bibdesk "Startup Behavior" -int 4

