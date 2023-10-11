# logic

## Tseitin's transformation)

## Semantics
a state <img width="9" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/10d5e8e0-b9f0-4c55-a3b6-38522360068b"> is a function from vars to Z；
</br>
<img width="402" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/76162df0-cf88-4863-a374-3d778698ee7f">
## Hoare logic
</br>
<img width="634" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/2cc638f2-7b2e-46bc-9c86-f15c95f2e831">
</br>

### 
<img width="433" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/2f7c6388-8271-4d22-8d7b-c64c6dad4f09">
</br>

### Invariants
Loop invariants:
holds before the loop
holds after each loop iteration
</br>
<img width="473" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/5663acd1-028f-4b43-b529-6c81909c40fd">

</br>
<img width="511" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/4cb65e90-573e-403c-b3bd-91d6b8f9a966">

</br>
<img width="350" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/c2542659-dc71-4d52-b366-a59d01bb7159">
</br>



### pointer

</br>
<img width="398" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/eda598f6-0451-4471-bbc3-1470480e5f67">
</br>

### Vcgen
</br>
<img width="405" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/19c79538-fb45-474f-b39e-d5f091ca85af">
</br>

### Horn clause

</br>
<img width="358" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/32a3cf90-1a7a-4816-abbb-e09a46649b41">


## non-Interference
A process A is said to be noninterfering with another process B across a system M if A’s input to M has no effect on M’s output to B. This property implies that no information flows from A to B through M. Noninterference expresses a confidentiality guarantee because if the observations of B are completely independent of the actions of A, then M does not leak anything to B about A’s input and A cannot reveal any secrets to B via M. Noninterference also expresses an integrity guarantee because if no information flows from A to B through M, then B cannot be corrupted by A via M.
