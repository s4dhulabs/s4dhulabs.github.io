---
layout: default
youtubeId: _kTUDjUrizg
---

## Running Djunch against Django Web Application

_Poc of Djunch fuzzer for Vimana Framework v0.3_

Djunch is a Django application fuzzer that can be invoked by other tools or directly via `vimana run --fuzzer <arguments>`:
![Alt text](https://github.com/s4dhulabs/s4dhulabs.github.io/blob/master/resources/imgs/run_fuzzer2.png?raw=true "VIMANAFRAMEWORK")

In this case we're kind of talking from a more whitebox perspective, since the fuzzer expects the `--url-conf` parameter with the application's `urls.py` as an argument, unless of course you're fuzzing an open source Django application with file access with URL patterns. However, other options are also supported and will be presented at another time.

After this step, the initial scope will be passed to DMT to expand URL patterns, that will result in something like:
![Alt text](https://github.com/s4dhulabs/s4dhulabs.github.io/blob/master/resources/imgs/run_fuzzer3.png?raw=true "VIMANAFRAMEWORK")

That will be the initial scope to feed Djunch, and so application fuzzing step can start:
![Alt text](https://github.com/s4dhulabs/s4dhulabs.github.io/blob/master/resources/imgs/run_fuzzer4.png?raw=true "VIMANAFRAMEWORK")

Note that the initial scope (the expanded url patterns) will be used by Djunch to create its own scope. From this, the traditional fuzzer flow is followed until the results consolidation phase, as can be seen in the DMT poc in the current version of the framework:
![Alt text](https://github.com/s4dhulabs/s4dhulabs.github.io/blob/master/resources/imgs/run_fuzzer_exception1.png?raw=true "VIMANAFRAMEWORK")

Traceback step:
![Alt text](https://github.com/s4dhulabs/s4dhulabs.github.io/blob/master/resources/imgs/run_fuzzer_exception_snipet1.png?raw=true "VIMANAFRAMEWORK")

For more information about the consolidation of results, check out [dmt](./dmt.html) example.


#       *   Keep abducting...  
#     (-_-)       
#     _) (_        
#    /__/  \            
#  _(<_   / )_          
# (__\_\_|_/__)                       




[back](./index.html)
