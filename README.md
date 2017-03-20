# uo-frida

UOSA dynamic instrumentation toolset based on https://www.frida.re/

I'm tired of messing with this in C++/C# so I ported it to frida (Python/Javascript) :)

# Installation

1. Install Python 3.6 from https://www.python.org/
1. Install frida toolkit through python package manager `pip` with `pip install frida`
1. Clone this repository (just into the UOSA folder will work): `git clone <this-repo-url>`
1. Open `config/config.py` and change the paths to UOSA folder and uofrida folder (dont forget double backslashes)
1. Start uofrida from the command line: `python uofrida.py`

# Configuration

All extensions under `js/extensions` have a `disabled` flag to quickly configure which extensions to load. Extensions come with an maturity rating. Disable experimental extensions if there are problems with them (like client crashing with access violation).

# Lua

There is a compiled LuaPlus dll in lib/. It's supposed to be very close to the LuaPlus version in UOSA. Feel free to compile it by yourself from sources but for sake of ease I just included my archived version.

# Extensions

## AddUOKeyboardFunctions

Adds new functions for calling from lua: `MoveMouseAbs`, `MouseLClick`, `MouseRClick`, `DICtrlShift`, `DIKey1`, etc.

## LuaNewState

Required for `AddUOKeyboardFunctions`. Keeps track of the lua state within the client and exposes it to our own functions. 