# logic
## Semantics
a state <img width="9" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/10d5e8e0-b9f0-4c55-a3b6-38522360068b"> is a function from vars to Z；
<img width="402" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/76162df0-cf88-4863-a374-3d778698ee7f">

## non-Interference
A process A is said to be noninterfering with another process B across a system M if A’s input to M has no effect on M’s output to B. This property implies that no information flows from A to B through M. Noninterference expresses a confidentiality guarantee because if the observations of B are completely independent of the actions of A, then M does not leak anything to B about A’s input and A cannot reveal any secrets to B via M. Noninterference also expresses an integrity guarantee because if no information flows from A to B through M, then B cannot be corrupted by A via M.
