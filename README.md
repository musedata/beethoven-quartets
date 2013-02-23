These MuseData files were used to print the PDF scores for Beethoven's
string quartets found on the [Beethoven String Quartets website](http://wiki.ccarh.org/wiki/Beethoven_String_Quartets#Scores_.28downloadable.29).



| Opus | Quartet | PDF | MPG | Stage 2  |
| ---- | ------- | --- | --- | -------- |
| 18/1 | No. 1   | [X](http://scores.ccarh.org/beethoven/quartets/beethoven-quartet01-op18n1.pdf) | [X](pages-score/beethoven-op018n1.pag) | [01](stage2/beethoven-op018n1-01.msd) [02](stage2/beethoven-op018n1-02.msd) [03](stage2/beethoven-op018n1-03.msd) [04](stage2/beethoven-op018n1-04.msd) |
| 18/2 | No. 2   | [X](http://scores.ccarh.org/beethoven/quartets/beethoven-quartet01-op18n2.pdf) | [X](pages-score/beethoven-op018n2.pag) | [01](stage2/beethoven-op018n2-01.msd) [02](stage2/beethoven-op018n2-02.msd) [03](stage2/beethoven-op018n2-03.msd) [04](stage2/beethoven-op018n2-04.msd) |
| 18/3 | No. 3   | [X](http://scores.ccarh.org/beethoven/quartets/beethoven-quartet01-op18n3.pdf) | [X](pages-score/beethoven-op018n3.pag) | [01](stage2/beethoven-op018n3-01.msd) [02](stage2/beethoven-op018n3-02.msd) [03](stage2/beethoven-op018n3-03.msd) [04](stage2/beethoven-op018n3-04.msd) |
| 18/4 | No. 4   | [X](http://scores.ccarh.org/beethoven/quartets/beethoven-quartet01-op18n4.pdf) | [X](pages-score/beethoven-op018n4.pag) | [01](stage2/beethoven-op018n4-01.msd) [02](stage2/beethoven-op018n4-02.msd) [03](stage2/beethoven-op018n4-03.msd) [04](stage2/beethoven-op018n4-04.msd) |
| 18/5 | No. 5   | [X](http://scores.ccarh.org/beethoven/quartets/beethoven-quartet01-op18n5.pdf) | [X](pages-score/beethoven-op018n5.pag) | [01](stage2/beethoven-op018n5-01.msd) [02](stage2/beethoven-op018n5-02.msd) [03](stage2/beethoven-op018n5-03.msd) [04](stage2/beethoven-op018n5-04.msd) |
| 18/6 | No. 6   | [X](http://scores.ccarh.org/beethoven/quartets/beethoven-quartet01-op18n6.pdf) | [X](pages-score/beethoven-op018n6.pag) | [01](stage2/beethoven-op018n6-01.msd) [02](stage2/beethoven-op018n6-02.msd) [03](stage2/beethoven-op018n6-03.msd) [04](stage2/beethoven-op018n6-04.msd)  [05](stage2/beethoven-op018n6-05.msd) |

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

# Parts

Part MPG files are not yet available.  Basic parts can be created
by extracting a single part file from the concatenated parts in the
stage2 directory.  The [examples](examples) directory contains separate 
stage2 MuseData part files for the first movement of string quartet 
No. 1, op. 18/1.

When a part is extracted to print by itself, you will have to change
two lines in the header for the part.  For example, change line 15 of
the cello part from:

<pre>
score: part 4 of 4
</pre>

to: 

<pre>
score: part 1 of 1
</pre>

Before sending it as input to muse2ps.  The muse2ps program only prints
scores, so the "parts" line underneath the "score" line in the file header
is ignored (muse2ps does not contain the part-generating code from dmuse).


