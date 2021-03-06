IMPORTANT NOTE:
---------------

STk is the ancestor of STklos (http://stklos.net).  The development of STk
has ceased in in September 1999 with the version 4.0.1.

The current repository contains all the versions from 3.1.1 (Sep'96) to
4.0.1 (Sep'99).

It also contains fixes to allow the compilation of 4.0.1 on modern versions
of GCC. Running STk on Win32 and MacOs is probably not possible
anymore (and there is no plan to assure so). 

Please, don't use this version, except for doing some IT archeology.

There are a lot of modern implementations of Scheme which are still
developed (STklos is one of them). Prefer a Scheme version which is still
maintained.

______________________________________________________________________



                    This is the release 4.0 of STk
                   -------------------------------


(Latest release is always available from <ftp://kaolin.unice.fr/pub/STk> )

STk is a R4RS Scheme interpreter which can access the Tk graphical
package.  Concretely it can be seen as the John Ousterhout's Tk
package where the Tcl language has been replaced by Scheme.

STk also provides an efficient object oriented system called STklos.
STklos is an extensive OO system with multiple inheritance, generic
functions, multi-methods and a Meta Object Protocol).

This release runs on majors Unix versions (Linux, Solaris, OSF, ...)

This version also runs on Win32. Consider this port as beta.

Version 4.0 uses the Tk 8.0.3 package for the graphical widgets.


DIFFERENCE PREVIOUS RELEASE
---------------------------

Only major changes are listed here. See the file 'CHANGES' in the
distribution main directory for more informations.


   * A module system has been added
   * Integration of the Bigloo MATCH-CASE and MATCH-LAMBDA
     primitives. Furthermore, the file bigloo.stk provide
     some compatibility between STk and bigloo modules.
   * A simple FFI has been added. It allows to access C
     functions without writing C code (works only on a
     limited set of architectures for now).
   * Integration of the Tk 8.0.3 toolkit
   * The MOP of STklos is now very similar to the CLOS one.
   * When a class is redefined, the instances and methods
     which uses it are redefined accordingly, as in CLOS.
   * Generic functions can be now traced with the standard
     TRACE function.
   * Some new composite widgets: Gauge, Valued-Gauge,
     Balloon-help, Notespad, Hierarchies, ...
   * The HTML-browser has been enhanced to access now the
     web (i.e. you can grab distant texts or images). The
     Web browser admit now applets written in Scheme.
   * Numerous bug corrections
   * Runs on Win32 platforms
   * New option -console to run STk in a windowed environment 
     (with indentation and fontification).
   * define-syntax
   * SRFI-{0,2,6,8,9}
   * New License Policy (request for commercial apps no more needed).
   * ...


SCHEME WITHOUT TK (for Unix Only)
-----------------

Standard make build a light version of STk which does not provide support for
the Tk toolkit. This interpreter, called Snow (Scheme with NO Window), can be
called directly with the 'snow' shell script. It is implicitly called if 
your DISPLAY variable is not set.

LEARNING STk
------------

In Contrib/STk-wtour, you'll find a program (called stk-wtour) which is a kind
of tutorial for programming widgets in STk. This program, which is a
contribution of Suresh Srinivas (ssriniva@cs.indiana.edu), is an excellent 
starting point for learning basics of STk widgets programming.

FILE ORGANIZATION
-----------------

    Stk
      |___ Contrib     The contributors directory
      |___ Demos       some original Tk demos rewritten for stk plus some other
      |                stuff found on  the net. 
      |___ Extensions  This directory contains extensions of the core interpreter
      |                (hash tables, POSIX.1 support). See the README file for more 
      |                details
      |___ Doc         Documentation of STk.                   
      |___ Help        Various (HTML) help files for STk.
      |___ Lib         a set of Scheme files used by the interpreter
      |___ Stack       files (very architecture dependant) for pushing args on 
      |                the C stack. Used by the FFI of STk.
      |___ Src         contains source files of stk (i.e. the sources files of the 
      |                interpreter + some glue files between Tk and Scheme).
      |___ Snow        contains (mostly) links over Src files. This directory 
      |                is used to build snow the Scheme interpreter without Tk
      |                support
      |___ STklos      an CLOS-like object extension of Scheme based on the
      |    |           Tiny CLOS package.
      |    |_ Tk       A library of Tk objects based on the STklos object
      |    |           extension package (subdirectory Composite contains
      |    |           composite widgets definitions        
      |    |_ Examples A (small) set of examples written in STklos.
      |___ Tcl         contains a set of unchanged files of the Tcl library which 
      |                pertain in Stk
      |___ Tk          contains a modified version of the Tk library. Most of the
      |                files are unchanged; Search the string ORIGINAL_CODE to see
      |                performed changes.
      |___ Win32       contains file necessary to compile STk under Win32

SUPPORTED ARCHITECTURES
-----------------------

For now, STk is known to run on the following machine/systems

        - Sparc (SunOs 4.1.x & Solaris 2.{34})
        - Dec 5xxx (Ultrix 4.2)
        - SGI (IRIX 4.05, 5.1.1, 5.2)
        - DEC Alpha 3000/400 (OSF-1 V1.3)
        - RS6000 AIX 3.2.5      
        - HP 9000/735 (HP-UX 9.01)
        - PC (Linux 1.0 -> 2.0)
        - PC (FreeBSD 1.1)        
        - PC (SCO)                
        - PC (NetBSD-1.0)         
        - Sony WS (Sony NEWS, NEWSOS 4.2R)
        - PowerPC running Linux
        - ...


Version 3.1.1 was also known to run on Windows 95 (and probably Windows NT).
The version 4.0 has also been ported on this environment and should be more 
stable than previous versions.


If you install it on another architecture/system, please let me now the
diffs you used such I can integrate them in the next release.

The file COMPILING-HINTS may be useful for compiling STk on your system.

DYNAMIC LOADING
---------------

Support for dynamic loading is provided for the following architectures/systems

                - SunOs 4.1.x
                - SunOs 5.3
                - NetBSD-1.0 (i386-port)
                - Linux (with the DLD package or ELF format). [ Dynamic
                  loading is disabled by default. Use -enable-elf or 
                  -enable-dld to choose the way you want to make dynamic 
                  loading under Linux]
                - FreeBSD
                - HPUX
                - SGI Irix 5.3 

IMAGE CREATION
--------------

The following architecture support image creation (dumping the interpreter 
memory in a file):
                - SunOs 4.1.x
                - Linux 1.1 (a.out format only)
                - FreeBSD

MAILING LIST
------------

Subscription/unsubscription/info requests to the STk mailing list
should be sent to 'stk-request@kaolin.unice.fr'

To subscribe to the mailing list, simply send a message with the word
"subscribe" in the "Subject:" field to the following address:
'stk-request@kaolin.unice.fr'

To unsubscribe from the mailing list, simply send a message with the
word (you guessed it :-) "unsubscribe" in the "Subject:" field to
'stk-request@kaolin.unice.fr'

For more information on the mailing list management send a message
with the word "help" in the Subject: field to the
'stk-request@kaolin.unice.fr'

Subscription requests are processed automatically without human
intervention. If you have a problem, send a mail to
eg@kaolin.unice.fr.

Messages sent to the mailing list are archived and can be browsed from
the STk home page.

STk W3 HOME PAGE
----------------

The STk W3 home page is located at
        http://kaolin.unice.fr/STk

BUGS
----

If you find a bug, please report it to stk-bugs@kaolin.unice.fr. 

AUTHOR ADDRESS
--------------

    Erick Gallesio                                    tel : (33) 92-96-51-53
    ESSI - I3S                                        fax : (33) 92-96-51-55
    Universite de Nice - Sophia Antipolis           email : eg(at)unice.fr
    Route des colles
    BP 145
    06903 Sophia Antipolis CEDEX
    FRANCE

     


     

