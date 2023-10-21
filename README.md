# logic
</br>
<img width="749" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/d22e216c-670d-4301-bef2-31e390ad79a1">
</br>
Sound：程序分析覆盖了所有的内容  
complete: 不会误报，但可能漏报
</br>
<img width="499" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/b73e4968-754b-4272-9748-023dda7e29d1">

</br>
- [propositional logic]
- [First order logic]

## propositional logic 
formula = conjunction ∧ of clauses
clause = disjunction ∨ of literals
literal = proposition or its negation

### NNF
Negation only appears in literals
### DNF
is a formula that is in DNF also in NNF?{YES}  
DNF conversion causes exponential blow-up in size.
### CNF

```
Consider the following formula (p→q) → (r∧¬p).  

Transform the formula into CNF form using the naive transformation (that is, not using Tseitin's transformation).   
A clause that only consists of a single propositional variable and its negation (e.g., the clause (p ∨ ¬p)) is trivially true.  
Remove such clauses from your solution. How many clauses does the translation have?
3 
```
### Tseitin's transformation
converts formula F to an equisatisfiable formula F' in CNF with only a linear increase in size.
</br>
<img width="524" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/66b53ff4-5081-432b-a6ec-db5b519d47f9">
</br>
<img width="410" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/2f69d804-ede7-4daf-9b1f-fcd5ecb916fa">

</br>
<img width="639" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/6af88fc7-179b-4acf-ab7f-1382b639cd2e">
</br>

### BCP

### PLP

```
Consider the following formula (r ∨ ¬p ∨ ¬s) ∧ (¬q ∨ p ∨ r) ∧ (r ∨ q) ∧ ¬r. 
We're trying to solve the formula using DPLL with BCP and PLP.  Assume the algorithm just picked the assignment r -> ⊥.
Apply BCP and PLP on the resulting formula. That is, exhaustively apply unit-resolution and pure literal propagation.

Remember, if you eliminate a variable p using unit resolution you may assume its assignment is ⊤.

What is the remaining formula and final variable assignment after exhaustively applying BCP and PLP?
```

##### exercises

```
Consider the following formula F in propositional logic F≙ (¬( p ∧ ¬q )) → (( q → r ) → ( p → r )). Consider assignment I≙ {p→ ⊥, q→ ⊤, r→ ⊤}.  
Which of the following statements is true?  

Formula F is true under assignment I, that is I ⊨ F, and formula F is valid. 
```

```
Consider the following propositional formula F ≙ p ∧ (q ∨ ¬r) ∧ (¬(¬q) ∨ r) ∧ r. Which of the following statements about F is true?  
F is satisfiable and not in CNF. 
```
## First order logic(predicate logic)
Propositional logic has very limited expressive power  
It is `undecidable` whether a first-order formula is valid
</br>
<img width="753" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/62e841ea-3d23-49db-8a85-08df9c3d332b">
</br>
### syntax
<img width="372" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/63b10af6-594f-4781-bcf3-b187287e6082">
</br>
<img width="644" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/4d87b563-fe5b-47c0-823f-aeeb4b56dc84">

</br>
which of the following are syntactically correct first order formulas?


:heavy_check_mark: f(x)  
:white_check_mark: g(x)  
:white_check_mark:p(f(x))  
:heavy_check_mark:p(p(x))  
:white_check_mark: p(f(g(x)))  

#### atomic predicate
<img width="723" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/67baa660-f665-4a92-8eba-54d4bc2eb388">
</br>

<img width="629" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/4d40b6e7-7f83-4d94-9959-722f365f9a4f">

#### first order formula
<img width="306" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/b12c9c53-1280-4816-9070-3be9d1ddf9b7">
</br>

a formula with no free variables is called a `closed` formula,or `sentence`.  
a formula with free variables is called `open`.  
a formula is called `ground` if it does not contain any variables.  
p(a,f(b))→q(c)
</br>
examples
</br>
<img width="400" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/6ad7e634-da86-489f-a86c-d97f0a5592e8">
</br>

### semantics
To give a semantics to FOL, we need to first fix a `universe of discourse`(Domain).
</br>
The universe of discourse is a `non-empty` set of objetcs we want to say something about.
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

#### how to evaluate a term t under interpretation I and assignment

#### semantic arguments
<img width="894" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/f4367fb0-961c-455e-81ab-58c0741b6fd0">  
is the formula（∃x.p(x)）→p(x) sat,unsat or valid? {SAt}  
(∀x.p(x))→p(x) sat,unsat or valid? {Valid}  
(∀x.(p(x)→q(x))→(∃x.(p(x) and q(x))) {SAT}  

consider a formula F such that S,σ |= F, is S a model of F? {NO}  
consider a sentence F such that S,σ|=F, is S a model of F?{YES}  
consider a ground formula F such that S,σ|=F, is S a model of F?{YES}  

### first-order theories
But undecidable makes decision procedures unpredictable  
we donot know if they will terminate  
Foucu on decidable fragments of FOL
That means, for some first order theory T:if a formula is valid in FOL, it is also valid modulo T  
but if a formula is valid modulo T,is it also valid in FOL {No}  
#### T =
<img width="452" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/1e4c0455-fc47-4d5e-8699-b8be8cb52d88">
</br>
The quantifier-free fragment of T= is decidable but NP-complete
</br>
<img width="446" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/51bb8d40-b635-4a15-ac6c-e965ab73d139">
</br>

```
Consider universe U ≙ {▢,◍,★}, where we have a single unary function f, a unary predicate p, and a single constant a.
Assume, we have variable assignment σ(x) = ★ and the following interpretation:

I(a) = ▢

I(f) = {★→◍, ◍→▢, ▢→★}

I(p) = {⟨★, ▢⟩, ⟨◍, ▢⟩, ⟨★, ★⟩, ⟨◍, ◍⟩, ⟨▢, ▢⟩} 

Now consider formulas 

F ≙ p(x, a) → p(f(x), a)

G ≙ ∃x.( p(x, x) → p(x, f(x)) )

Let S = ⟨U, I⟩. Which of the following statements is true
S, σ ⊨ F and S, σ ⊨ G, that is, both F and G are true.


```


#### Peano Arithmetic
<img width="480" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/9afcc271-c825-42f0-b034-002d775f5b0b">
</br>
Validity in full Peano and even the quantifier0free fragment of Peano Arithmetic is undecidable
</br>
<img width="477" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/e5231f83-0a51-4489-b08d-6b372cd5790d">

#### Presburger arithmetic
drop multiplication  
validity in quantifier-free and full Presburger arithmetic is decidable, but super exponential complexity.
</br>
<img width="470" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/3b05b898-31d7-493f-9197-fefbd22b97ad">
#### Integer Arithmetic (linear arithmetic over integers)
equivalent in expressiveness to Presburger arithmetic

#### Theory of Rationals
Full theory of rationals is decidable, but doubly exponential  
Conjunctive quantifier-free fragment efficiently decidable (polynomial time)  

</br>
<img width="508" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/64adbb67-a9ef-4475-a48e-dded56f8cc9c">

</br>
<img width="471" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/d622fb99-ae71-4acd-acb6-ed2466b5fad2">

#### Theory of arrays
<img width="501" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/d5f43a6f-bbe5-4755-a04a-2c84eaba9885">
</br>
= is only defined for array elements  
</br>
<img width="460" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/915e9607-ad23-47cf-bac3-81d5665b8f84">
</br>
<img width="350" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/0365da6b-692d-46e5-a274-1ad7a9f27e5c">

</br>





## Hoare logic
Hoare logic is a formalism for relating the initial and terminal state of a program.  
</br>
<img width="469" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/16d895d6-ce18-4460-acbe-0f94d56fcd39">

</br>
Hoare logic is a way of inserting annotations into code to make
proofs about (imperative) program behavior simpler.
</br>
<img width="523" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/dcc1b93e-d55c-41f2-9888-a449e07e76c2">

</br>

</br>
<img width="634" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/2cc638f2-7b2e-46bc-9c86-f15c95f2e831">
</br>
</br>
<img width="362" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/53d037ee-3426-4cf3-9167-15cb67752545">
</br>

### partial correctness
<img width="532" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/bd18304e-ede3-491e-b35e-aec37d118277">
</br>

#### corner cases
<img width="531" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/02099b81-53d9-41bd-8924-22339045a42e">

### proof roles
<img width="525" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/c1d0a20d-80f3-4bfa-a87e-f5dbb45e3c74">
</br>
<img width="510" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/7eb8437e-9ecd-4130-8e2a-795029def187">

</br>
<img width="515" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/0943a748-f92d-493f-8cf8-f3ea94d468a6">
</br>
<img width="508" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/d220396f-434f-4a58-a0cc-98f9eaf10e7a">

</br>
<img width="502" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/54063e99-8f7b-427b-93e2-c6f353a0bc48">

</br>
<>
####

### Semantics
a state <img width="9" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/10d5e8e0-b9f0-4c55-a3b6-38522360068b"> is a function from vars to Z；
</br>
<img width="402" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/76162df0-cf88-4863-a374-3d778698ee7f">



### WP Postcondition Weakening
</br>
<img width="437" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/faea73af-4428-42bc-8ad7-77bde2690860">

</br>
we need to use an SMT solver when applying post-conditioon weakening  
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

### Vcgen(verification condition generation)
the general steps:  
<img width="581" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/19477022-e6ad-4a64-9d55-cdaff1b018b1">


</br>
<img width="405" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/19c79538-fb45-474f-b39e-d5f091ca85af">
</br>
<img width="526" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/6d578847-2ff4-4e05-99ca-2404c9542792">
</br>
<img width="546" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/ec076f98-3336-4e85-9b36-9e9733216cde">
</br>

#### Soundness of Hoare logic
<img width="577" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/33a6e7bc-611a-47f5-945e-f7133fc61d7a">

#### completeness
<img width="589" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/9f6b1b7e-079b-4bcb-b279-d2c2754ef05b">

#### Hoare logic exercises
<img width="557" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/56e907dd-a43f-431d-b48e-c4e081149755">
</br>

### Horn clause
Horn clauses represent constraints on unknown relations called queries.  
use weakest preconditions to translate programs into Horn clauses, this translation uses queries to represnet loop invariants.
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
the solutions to the queries give us the missing loop invariants  
(1)start with a solution that maps all queries to false  
(2)Pick any clause whose head is q query  
(3)then use the post operator to compute strongest postconditions  
(4)
##### subsumption check
<img width="355" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/0d71c027-adf9-420f-8f2b-3bb3f182227d">
</br>
##### use abstraction to solve terminates
我们将程序在执行过程中，所有可能出现的状态视为一个集合，称为程序的实际状态集合，记为C。一般而言，集合C是难以获得和准确描述的，而直接在C上进行分析是困难的，其代价也非常高。因此，我们需要使用近似思想，在一个更加“简洁”的集合上进行分析，从而提高效率。在下近似分析中，会在一个C的子集U中进行分析；而在上近似分析中，则会在一个C的超集O中进行分析。  
为了保证分析的正确性（Soundness），下近似分析一般只用于找错（证伪，Falsification），但无法用于证明（Verification）。这是因为，在实际状态集C的子集U中寻找到的可达错误状态，一定也是C中的可达错误状态。反之，U中不存在可达错误状态却不能说明C中亦不存在可达错误状态。软件测试可以视为一种下近似分析；
上近似分析则一般只用于证明，而不直接用于找错。这是因为在实际状态集C的超集O中不存在可达的错误状态，那么C中一定也不存在可达错误状态。反之，O中存在可达的错误状态，却不能说明C中亦存在可达的错误状态。一般基于抽象的方法，比如静态分析中的各类基于抽象解释的分析算法，程序验证中的谓词抽象、路径抽象等等，都是上近似分析；引入不变式也是一种上近似。  
instead of the concrete post, we compute an abstract post post#  
</br>
<img width="355" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/2d32abd7-f9e8-4f81-8089-7367a68fd10b">

</br>

</br>
<img width="349" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/e8e400be-736b-41a4-916e-8fa097a50a49">

</br>



##### fixedpoint theorem Kleene
##### abstract interpretation

# Security
side-channels& speculation

## non-Interference
A process A is said to be noninterfering with another process B across a system M if A’s input to M has no effect on M’s output to B. This property implies that no information flows from A to B through M. Noninterference expresses a confidentiality guarantee because if the observations of B are completely independent of the actions of A, then M does not leak anything to B about A’s input and A cannot reveal any secrets to B via M. Noninterference also expresses an integrity guarantee because if no information flows from A to B through M, then B cannot be corrupted by A via M.
</br>
<img width="364" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/247c7aa5-0940-4261-8fc2-52dd6cf7ab4c">

</br>

## attacker model
</br>
<img width="348" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/44a9974d-4324-43b6-9387-e6319904fc37">

</br>

## Information flow
publicly observable information, and secret information  
To ensure confidentiality, flowing information from high to low variables should not be allowed.  
More generally, the security levels can be viewed as a lattice with information flowing only upwards in the lattice  
For example, considering two security levels L and H (low and high), if L ≤ H,flows from L to L, from H to H, and L to H would be allowed, 
while flows from H to L would not.  
</br>
<img width="355" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/d2a3e67f-5bf8-48cc-a46b-39780a86baff">
</br>
<img width="337" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/1959c70e-3255-4d0d-b7f4-fa420ad82c52">

### Explicit flows and side channels
<img width="697" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/04b3eb53-7b29-4405-ae73-ad463f63518a">

### time attack
In cryptography, a timing attack is a `side-channel attack` in which the attacker attempts to compromise a cryptosystem by analyzing the time taken to execute cryptographic algorithms. Every logical operation in a computer takes time to execute, and the time can differ based on the input; with precise measurements of the time for each operation, an attacker can work backwards to the input.

## Security type system
In a programming language augmented with a security type system every expression carries both a type (such as boolean, or integer) and a security label.
## Speculative Execution

# literature
程序分析与验证中的近似思想  
https://github.com/barghouthi/cs704  
https://theory.stanford.edu/~arbrad/slides/  
Hoare logic:  
https://www.cl.cam.ac.uk/teaching/2021/HLog+ModC/slides/
