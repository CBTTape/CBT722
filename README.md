# CBT722
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE 722 is from Shirley Huhtanen and contains the FileWiz     *   FILE 722
//*           package which is a sophisticated program that         *   FILE 722
//*           compares 2 files.  More detailed description of       *   FILE 722
//*           the FileWiz package may be found below.               *   FILE 722
//*                                                                 *   FILE 722
//*  FileWiz    (c) 2005                                            *   FILE 722
//*                                                                 *   FILE 722
//*  Renaissance Data Systems Inc.                                  *   FILE 722
//*  Shirley Huhtanen                                               *   FILE 722
//*  3325 Lorna Rd 2-325                                            *   FILE 722
//*  Birmingham, AL  35216                                          *   FILE 722
//*  (205) 999-9012                                                 *   FILE 722
//*  email: shirleywho@aol.com                                      *   FILE 722
//*                                                                 *   FILE 722
//*  This library is a self-contained unit and should contain all   *   FILE 722
//*  of the elements needed to set up the File Compare program.     *   FILE 722
//*                                                                 *   FILE 722
//*  Description                                                    *   FILE 722
//*                                                                 *   FILE 722
//*   FileWiz is a program (JXCU001) that compares 2 files.         *   FILE 722
//*                                                                 *   FILE 722
//*   What's special about it?                                      *   FILE 722
//*     1.  It's free.                                              *   FILE 722
//*     2.  The source is provided.                                 *   FILE 722
//*     3.  It has some unique Masking features.                    *   FILE 722
//*     4.  The positional summary of differences at the end        *   FILE 722
//*         saves a LOT of time.                                    *   FILE 722
//*     5.  All non-matching records are written out for further    *   FILE 722
//*         analysis.                                               *   FILE 722
//*                                                                 *   FILE 722
//*   A key must be identified that will match up the records       *   FILE 722
//*   in both files.  The key does not have to be contiguous        *   FILE 722
//*   but it does have to be ascending.                             *   FILE 722
//*                                                                 *   FILE 722
//*   Differences are shown in a difference report.                 *   FILE 722
//*   Differences are also written to output files that can be      *   FILE 722
//*   used for further analysis.                                    *   FILE 722
//*                                                                 *   FILE 722
//*   This file compare can't compare text files like program       *   FILE 722
//*   source, so it is better to use Superc (IBM) or another        *   FILE 722
//*   compare utility to compare text files.                        *   FILE 722
//*                                                                 *   FILE 722
//*   This file compare is written in Cobol.  It isn't as fast      *   FILE 722
//*   as file compares written in assembler, but the Cobol          *   FILE 722
//*   optimizer does a pretty good job of creating a fast product.  *   FILE 722
//*                                                                 *   FILE 722
//*   There are 3 kinds of masks that can be used.                  *   FILE 722
//*                                                                 *   FILE 722
//*     MASK      Completely masks the data for the offset          *   FILE 722
//*               and length specified                              *   FILE 722
//*     Signmask  Allows unsigned numeric data to                   *   FILE 722
//*               match positive signed data for packed decimal     *   FILE 722
//*               and zoned decimal fields                          *   FILE 722
//*     Nullmask  Allows spaces to match to low-values              *   FILE 722
//*               for filler areas                                  *   FILE 722
//*                                                                 *   FILE 722
//*   A really nice feature is the compare summary at the end of    *   FILE 722
//*   the difference report.  You can tell at a glance which fields *   FILE 722
//*   did not match.  This saves you from having to browse through  *   FILE 722
//*   every difference in the report to see if the same field was   *   FILE 722
//*   responsible for all the differences.                          *   FILE 722
//*                                                                 *   FILE 722
//* History of this Compare Program.                                *   FILE 722
//*                                                                 *   FILE 722
//*   During my consulting years, I worked at several companies     *   FILE 722
//*   that had not purchased a compare product.  After writing a    *   FILE 722
//*   different compare at each company for my own projects, I      *   FILE 722
//*   realized that I couldn't count on having a compare product    *   FILE 722
//*   available, so I wrote this FileWiz program and have used it   *   FILE 722
//*   and modified it to fit my needs.                              *   FILE 722
//*                                                                 *   FILE 722
//*   Since this is not intended to be a "commercial" product,      *   FILE 722
//*   (make money) there are a few cosmetic glitches here and       *   FILE 722
//*   there, where page breaking isn't completely clean.  The       *   FILE 722
//*   compares themselves are completely accurate.  My coding       *   FILE 722
//*   standards have changed over the years and I don't consider    *   FILE 722
//*   this program up to my current standards.  If I ever get       *   FILE 722
//*   the time (yeah right), I'll clean it up.                      *   FILE 722
//*                                                                 *   FILE 722
//*   Disclaimers                                                   *   FILE 722
//*                                                                 *   FILE 722
//*   This material is provided as-is.  It works on the z/OS        *   FILE 722
//*   system it was developed on, but may not work on all systems.  *   FILE 722
//*   No warranty is made to the accuracy of the programs or        *   FILE 722
//*   related material and no responsibility is assumed for any     *   FILE 722
//*   modifications made to these applications by a third party.    *   FILE 722
//*   The documentation included is intended to aid in setting up   *   FILE 722
//*   the systems.  Validating the results is the responsibility    *   FILE 722
//*   of the party using this material.                             *   FILE 722
//*                                                                 *   FILE 722
//*   These programs are distributed on the CBT Tape with the       *   FILE 722
//*   proviso that they may be freely distributed to any other      *   FILE 722
//*   party on condition that no inducement beyond reasonable       *   FILE 722
//*   handling costs is offered or accepted by either side for      *   FILE 722
//*   such distribution or your normal consulting costs for         *   FILE 722
//*   installation and support.                                     *   FILE 722
//*                                                                 *   FILE 722
//*   The use of any part of these programs or copybooks in         *   FILE 722
//*   another program or application does not make that program     *   FILE 722
//*   or application fall under this license.                       *   FILE 722
//*                                                                 *   FILE 722
//*   Modified versions of these programs and systems should *NOT*  *   FILE 722
//*   be distributed by a third party.  It will be chaos if         *   FILE 722
//*   multiple versions of this program starts floating around.     *   FILE 722
//*   If you have ideas for revision, please communicate them       *   FILE 722
//*   to the author.                                                *   FILE 722
//*                                                                 *   FILE 722
//*   This documentation has not had a work-out by being used to    *   FILE 722
//*   install the system on another machine.  Please contact me if  *   FILE 722
//*   you have any questions regarding any part of this product.    *   FILE 722
//*                                                                 *   FILE 722
```
