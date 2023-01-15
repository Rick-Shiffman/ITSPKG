# ITSPKG




Minimal Package System for ITS Muddle

Hi Everyone latest version, TT:RRS;ITSPKG >, my  minimal ITS Muddle Package system is ready
For peop[le to expriment with  report bugs to me at rrs0@earthlink.net and I will work on them. At the present
Time I didn't add support for rpackages and my TRANSLATE? Just returns the string it given. The realmTRANSLATE?
TRANSLATE AND UNTRANSLATE are still MIM code and commented out. L-SEARCH-PATH is SETGed to 
(<SNAME>  "MUDDLE") and FIND/LOAD looks for FN1 = package-name, and FN2 = ">".

To experiment with this package system, Start an ITS MUDDLE and load PPRINT to help maintain your sanity 
After this FLOAD t:rrs;itspkg > to load the package system. Then USE package-name to load the package you wanted.
Below is an example of how to run MIGS, all in t:rrs; directory. TRANS translates graphics coordinates in the character
Codes used by the graphics terminal. MIGSSEND sends these character codes to your terminal. When starting MIGS
Use "A" Ards and Imlacs or enter "H" for the help documentation. "T" is for Tektronix 4010 type terminals
	
...........................................
	
*MDL$^K!
MUDDLE 56 IN OPERATION.MUDDLE INIT
	
PPRINT? (Y OR N) space is yes too /PPRINT/FRAMES
	
LISTENING-AT-LEVEL 1 PROCESS 1
	
<FLOAD "ITSPKG >">$
"DONE"
  
;"load a factorial test package"
<USE "F">$
<F 3>;"test it"$
6

<USE "MIGSPK">$

Muddle Interactive Graphics System
Enter terminal code or 'H' (help):T
	
 TEKTRONIX PRIMITIVES LOADED


MIGS LOADED
USE

;" test the MIGS primative terminal output function"
<PPRINT MIGSSEND>$

<DEFINE MIGSSEND ("TUPLE" LIST)
	#DECL ((LIST) <TUPLE [REST FIX]> (VALUE) ATOM)
	<MAPF <> ,IMAGE .LIST>
	,NULL>

<MIGSSEND 10 13 64 65 66 32 67 68 69 10 13>$

@AB CDE

.............................................
