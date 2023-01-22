# Python scripts
exploreValue.py:
    Convert values sets to specific function in human readable format.

parseQEmuOutput.py:
    Parse the output of QEmu customized with a patch which returns a files which contains sent CORB value (format 0x???????? per line) and received RIRB value (format  => RET: 0x???????????????? per line). It rewrites the raw corb value and a human readable format on the same line.

addTimeToCorbs.py:
    Rewrite the file got from "parseQEmuOutput.py" by prepending each line with a relative timestamp following the output of QEMU.

lineCorbs.py:
    Get the corb value, its human readable format and the associated returned RIRB value on the same line and numbers each line.
    An option is available to only extract corbs for NID 0x0, 0x6 and 0x20

splitCorbs.py:
    Does the same thing as lineCorbs but save the result on new files: one per NID. The output file is of the format "input file name"-NID.txt

parseProcCoef.py:
    Parse the output of "lineCorbs.py" or "splitCorbs.py" and rewrite in a more human readable format proc coef setting and getting.
    Note that if a coef is set just after it has been got it convers this action into an "update" and show the XOR between the value read and the value written.

parseRawVerb.py:
    Parse the verbs got from the Linux HDA tracing system. It does the same thing as "parseQEmuOutput.py" but for Linux HDA tracing system.

verbToPython.py:
    Custom script which converts the output of "parseProcCoef.py" to a python scripts. In particular it minimize the setting of many proc values and recognize two kinds of specific registers management which really improve the reading of verb managements. As far as I know these specific registers management are not often used by Realtek chips.


# Python libraries
extractVerb.py:
    Tool which converts a verb to a human readable format.

verbUI.py:
    Functions used by scripts generated by verbToPython.py
