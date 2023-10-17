# logic
[toc]
## propositional logic 

## First order logic(predicate logic)
Propositional logic has very limited expressive power
</br>
<img width="753" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/62e841ea-3d23-49db-8a85-08df9c3d332b">
</br>
### syntax
<img width="372" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/63b10af6-594f-4781-bcf3-b187287e6082">
</br>
<img width="644" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/4d87b563-fe5b-47c0-823f-aeeb4b56dc84">

</br>

#### atomic predicate
<img width="723" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/67baa660-f665-4a92-8eba-54d4bc2eb388">
</br>

<img width="629" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/4d40b6e7-7f83-4d94-9959-722f365f9a4f">

#### first order formula
<img width="306" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/b12c9c53-1280-4816-9070-3be9d1ddf9b7">
</br>

a formula with no free variables is called a *closed* formula,or *sentence*.
</br>

a formula is called *ground* if it does not contain any variables.
</br>
examples
<img width="400" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/6ad7e634-da86-489f-a86c-d97f0a5592e8">
</br>

### semantics
To give a semantics to FOL, we need to first fix a universe of discourse(Domain).
</br>
The universe of discourse is a non-empty set of objetcs we want to say something about.
</br>
can be finite,countably infinite, uncountably infinite, but can not be empty.
</br>
<img width="429" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/63dda6f6-086e-48e2-925a-e30e86059a39">
</br>


*A first order interpretation does not talk about variables, only constants.*
</br>
examples
<img width="373" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/e2b88bbc-739a-42c0-99cd-448e427e08a4">

</br>

#### how to evaluate a term t under interpretation I and assignment */sigma*

#### semantic arguments
<img width="894" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/f4367fb0-961c-455e-81ab-58c0741b6fd0">

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
#### why horn clause
motivation:
<img width="195" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/35b8018b-3bdb-4036-bc8a-3cffd0a421f6">

</br>
<img width="208" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/1db98387-2a0f-436d-8a6c-fe99c7d73232">

</br>
<img width="358" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/32a3cf90-1a7a-4816-abbb-e09a46649b41">
</br>

#### Non-recursive clause are easy to solve
#### Solving recursive clauses is undecidable& amounts to finding loop invariants.

#### Normalizeing Horn Clauses
#### solving Horn clauses
we can use *post* to compute a solution for a set of Horn clauses


## non-Interference
A process A is said to be noninterfering with another process B across a system M if A’s input to M has no effect on M’s output to B. This property implies that no information flows from A to B through M. Noninterference expresses a confidentiality guarantee because if the observations of B are completely independent of the actions of A, then M does not leak anything to B about A’s input and A cannot reveal any secrets to B via M. Noninterference also expresses an integrity guarantee because if no information flows from A to B through M, then B cannot be corrupted by A via M.
