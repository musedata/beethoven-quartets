These MuseData files were used to print the PDF scores for Beethoven's
string quartets found on the [Beethoven String Quartets website](http://wiki.ccarh.org/wiki/Beethoven_String_Quartets#Scores_.28downloadable.29)

# Directories 

## stage2

The stage2 directory contains stage-2 (notation-level) MuseData
files for the string quartets.  One file contains all parts for a
single movement (73 files total for 72 movements).  The file
beethoven-op135-04a.md2 contains the melodic fragment at the start
of the fourth movement of Op. 135.  Op. 133 (Grosse Fugue) is a
single-movement work.  

Files in this directory can be converted to PostScript files with
the [muse2ps](http://muse2ps.ccarh.org) command-line utility, or
processed inside of the [dmuse](http://dmuse.ccarh.org) environment.

Here is a basic [example](examples) of converting a MuseData file
into graphical notation.  This example uses the
[muse2ps](http://muse2ps.ccarh.org) to automatically typeset the
symbolic musical data in the MuseData file.  [Various
options](http://wiki.ccarh.org/wiki/Muse2ps#Options) are available
for controlling the automatic layout of the music on the page.

<pre>
   cat stage2/beethoven-op018n1-01.msd | muse2ps =z16j \
      | ps2pdf -sPAPERSIZE=letter  - - &gt; beethoven-op018n1-01.pdf
</pre>


## pages-score

The pages-score directory contains MPG (music page) files which are generated
from the stage2 files.  Each MPG file contains all of the pages for one
string quartet.  These files contain manually typeset music using the
[Dmuse](http://dmuse.ccarh.org) environment (muse2ps is a command-line
version of several processing programs found in Dmuse).

These page files can be converted into PostScript files with the muse2ps
program by using the =p option:

<pre>
   cat pages-score/beethoven-op018n1.pag | muse2ps =p \
      | ps2pdf -sPAPERSIZE=letter  - - &gt; beethoven-op018n1.pdf
</pre>

## footer

The footer directory contains descriptions of page footers which are added
to the final PDFs of the graphical music. 

