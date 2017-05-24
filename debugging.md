# Debugging in Python 3.6: Better, Faster, Stronger by Elizaveta Shashkova
## New frame evaluation API
 * `dis` package for returning bytecode in human-readable format
 * Don't need to call tracing function on every line any more, program runs almost as fast with debugger running (but run into slowness if debugging loop body)
## PEP 523 - Added `co_extra` to `PyCodeObject` function for scratch space (helps reduce number of times we add frames)
 * Handle evaluation of frames
 * Add a new field to code objects
## Results
 * PyCharm 2017.1 works in production
