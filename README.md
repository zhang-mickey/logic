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
F is `contingent` iff it si satisfiable but not valid  
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
Naive ways of checking SAT: Truth table and Deductive proofs  
Checking SAT efficiently via normal forms & DPLL.  
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
### DPLL(T)
This use of DPLL parameterized with respect to a set of theories T is called DPLL(T).  
(1)DPLL(T) does not use the pure variable elimination.  This is because, with theories, variables may be dependent.  


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

Theories we need for reasoning about programs: Equality, Arithmetic, Data-structures: Arrays.  
#### T =
Only = is "interpreted"  
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
Validity in full Peano and even the quantifier-free fragment of Peano Arithmetic is undecidable
</br>
<img width="477" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/e5231f83-0a51-4489-b08d-6b372cd5790d">

#### Presburger arithmetic(could prove that 2 × x = x + x)
drop multiplication  
validity in quantifier-free and full Presburger arithmetic is decidable, but super exponential complexity.
</br>
<img width="470" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/3b05b898-31d7-493f-9197-fefbd22b97ad">
#### Integer Arithmetic (linear arithmetic over integers)(LIA)
equivalent in expressiveness to Presburger arithmetic

#### Theory of Rationals
Full theory of rationals is decidable, but doubly exponential  
Conjunctive quantifier-free fragment efficiently decidable (polynomial time)  

</br>
<img width="508" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/64adbb67-a9ef-4475-a48e-dded56f8cc9c">

</br>
<img width="471" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/d622fb99-ae71-4acd-acb6-ed2466b5fad2">

#### Theory of arrays（ could prove that assigning x[y] to 3 and then looking up x[y] yields 3）
The quantifier-free fragment of TA is decidable.  
<img width="501" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/d5f43a6f-bbe5-4755-a04a-2c84eaba9885">
</br>
= is only defined for array elements  
</br>
<img width="460" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/915e9607-ad23-47cf-bac3-81d5665b8f84">
</br>
<img width="350" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/0365da6b-692d-46e5-a274-1ad7a9f27e5c">

</br>

```
Say, we extend Nano with a new expression ✴, that is described via the following inference rule, where ℤ denotes the integers. 

              n ∈ ℤ
--------------------------

         ⟨ ✴, σ⟩⇓ n

Say we're given the following program s:

x := ✴; y:=y+1

Let σ be an initial state such that σ(x)=0, and let ⇓ be the evaluation relation for expressions, including the new rule.

Which of the following statements is true?

Correct answer
 ⇓ is not a function and there exists σ’ such that ⟨ s, σ ⟩⇓ σ’ and σ’(x)=σ’(y).
```
#### combinations of theories
if
the quantifier-free fragment of T1 is decidable  
the quantifier-free fragment of T2 is decidable  
T1 and T2 meet certain technical requirements  
then the quantifier-free fragment of T1 and T2 is also decidable.  


## Hoare logic(endoce proofs abount programs)(Axiomatic semantics)
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
'''
Hoare Logic

Consider the following program L, which first executes a loop, and then a second statement s.

while i>0 do {i:=i+1}; s

Say, we are interested in whether the Hoare triple {⊤} L {Q} is valid, i.e., if  ⊨ {⊤} L {Q} holds.

For which of the following choices of s and Q is the Hoare triple valid.

  Q=⊤ and s= assert(⊥) 
  Q=⊥ and s= assert(⊤) 
Correct answer
  Q=⊥ and s= assume(i>0) 
'''
### operational semantics
A state is a function from vars to Z, captures the current value of all variables.  
Expressions evaluate to a number or Boolean value  
statements have no direct result, they yield a new program state.  

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
<img width="512" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/9578dcf5-ce3d-4ada-a12f-8cce06727225">
it shows that   how to pose the search for a Hoare-logic annotation as a search for a relation r(x,y,z) over program variables.  
We can generate a set of constraints whose models give solutions of r.


### Semantics
a state <img width="9" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/10d5e8e0-b9f0-4c55-a3b6-38522360068b"> is a function from vars to Z；
</br>
<img width="402" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/76162df0-cf88-4863-a374-3d778698ee7f">



### WP Postcondition strengthening
wp(s,Q) denotes the weakest formula that needs to hold before s, to ensure that Q holds after s.  
</br>
<img width="437" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/faea73af-4428-42bc-8ad7-77bde2690860">

</br>
we need to use an SMT solver when applying post-conditioon weakening  
</br>
<img width="433" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/2f7c6388-8271-4d22-8d7b-c64c6dad4f09">
</br>

### Invariants
Loop invariants:
holds before the loop
holds after each loop iteration
```
Hoare Logic and Invariants

We want to verify that a loop L has postcondition Q when executed under pre-condition P, that is, we want to prove the Hoare triple {P} L {Q}.

Let L ≙ while b do s. We want find an invariant I and use the Hoare rule for while loops, i.e., the rule that says, to prove ⊢{I} while b do s {I ∧¬b}, we need to prove ⊢{I ∧ b} s {I}, together with pre-condition strengthening and post-condition weakening. Which of the following statements about I is not true.

  I needs to be an invariant. 
  I needs to be inductive. 
  I needs to imply Q.  Correct!
```

```
Consider the following program:

assume(n≥0);i=0;j=n; while i < n  do {i := i + 1; j := j - 1}

We want to use the Hoare logic While rule to prove that j≤0 holds after the program.

Say, your friend suggests the following candidate for invariant I= (n≥i+j), i.e., the invariant states that 
n is larger or equal to i plus j.

Which of the following statements is true.

Correct answer
  The proof works out; I is an an inductive invariant that implies the post-condition.
```
</br>
<img width="473" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/5663acd1-028f-4b43-b529-6c81909c40fd">

</br>
<img width="511" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/4cb65e90-573e-403c-b3bd-91d6b8f9a966">

</br>
<img width="350" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/c2542659-dc71-4d52-b366-a59d01bb7159">
</br>





### Vcgen(verification condition generation)
The weakest precondition of a loop is its invariant, but we still need to check that the invariant is inductive.  
This requires side-conditions, which we generate via function vc.  
the general steps:  
<img width="581" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/19477022-e6ad-4a64-9d55-cdaff1b018b1">


</br>
<img width="405" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/19c79538-fb45-474f-b39e-d5f091ca85af">
</br>
<img width="526" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/6d578847-2ff4-4e05-99ca-2404c9542792">
</br>
<img width="546" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/ec076f98-3336-4e85-9b36-9e9733216cde">
</br>

### Functions
precondition and postcondition are called `function contact`.
### pointer
why we need to enhance rule of substitution
</br>
<img width="627" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/52dcc232-0e52-4a2a-835f-3924e772d67c">
</br>
Due to aliasing, an assignment ⭐x:=e can affect values of expressions beyongd ⭐x.  
```
Weakest Preconditions & Pointers

Consider the following Hoare triple we want to prove about a program containing pointers {⊤} *q := 4; *p := q; x := *p {x≥0}.

Let's use Pre to denote the weakest precondition of *q := 4; *p := q; x := *p with respect to x≥0 and let μ to denote the memory. Which of the following statements is true? 


  The Hoare triple does not hold, and Pre = μ<q◁4><p◁q>[p]≥0. Correct!
```
</br>
<img width="398" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/eda598f6-0451-4471-bbc3-1470480e5f67">
</br>  

</br>

</br>
https://github.com/barghouthi/cs704/blob/master/notes/cs704-lec-04-19-2010.pdf

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
Free variables are implicitly universally quantified.  
```
Horn Clauses

Consider the following set of Horn clauses ℂ.

(1)   y=x → p(x,y) 

(2)   p(x,y) → q(x,y) 

(3)   q(x,y) ∧ y'=y+2 ∧ x'=x-1  → p(x',y') 

(4)   q(x,y) → y>x

Your friend proposes the following solution: Σ ≙ {p(x,y)→(x=y), q(x,y)→(y≥x+1)}, that is, the solution maps p to x=y and q to y≥=x+1.

Which of the following statements is true?

  Σ is not a solution, i.e., Σ ⊭ ℂ, and ℂ is not recursive. 
  Σ is a solution, i.e., Σ ⊨ ℂ, and ℂ is recursive. 
  Σ is a solution, i.e., Σ ⊨ ℂ, and ℂ is not recursive. 

  Σ is not a solution, i.e., Σ ⊭ ℂ, and ℂ is recursive. Correct!
```
#### why horn clause
motivation:
<img width="195" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/35b8018b-3bdb-4036-bc8a-3cffd0a421f6">

</br>
<img width="208" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/1db98387-2a0f-436d-8a6c-fe99c7d73232">

</br>
<img width="358" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/32a3cf90-1a7a-4816-abbb-e09a46649b41">
</br>
</br>
<img width="454" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/5f0d9b92-67b6-4be6-b108-b7b029986806">

</br>

#### From programs to Horn Clauses
For an if-statement, introduce a fresh query.  
While loopsare no longer annotated with invariants. 

#### Non-recursive clause are easy to solve
<img width="644" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/3a353096-2a94-4849-903e-f073ad73d7af">

#### Solving recursive clauses is undecidable& amounts to finding loop invariants.

#### Normalizeing Horn Clauses
q(x,y) → p(x+1,y) {X}  
q(x) → x<n {X}  

#### (Naive) solving Horn clauses
we can use *post* to compute a solution for a set of Horn clauses  
the solutions to the queries give us the missing loop invariants  
(1)start with a solution that maps all queries to false  
(2)Pick any clause whose head is q query  
(3)then use the post operator to compute strongest postconditions  
(4)
```
Horn Clause Solving:

Say we are given a set of Horn clauses C, such that the head of all clauses is a query. Let's add another clause b, whose head is ⊥. Let's further assume, we are given a set of predicates P, and we're computing a solution by applying our solving algorithm to the set C ∪ b which produces a solution Σ. Which of the following statements is true?

  If Σ ⊭ b, then there is no Σ' such that Σ' ⊨ b. 
  It is always true that Σ ⊨ b, that is, that the solution satisfies b. 

  If Σ ⊭ b, then there might or might not be a solution Σ' to C ∪ b such that Σ' ⊨ b. Correct!
```
##### subsumption check
<img width="355" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/0d71c027-adf9-420f-8f2b-3bb3f182227d">
</br>

##### use abstraction to solve terminates(always terminates)
我们将程序在执行过程中，所有可能出现的状态视为一个集合，称为程序的实际状态集合，记为C。一般而言，集合C是难以获得和准确描述的，而直接在C上进行分析是困难的，其代价也非常高。因此，我们需要使用近似思想，在一个更加“简洁”的集合上进行分析，从而提高效率。在下近似分析中，会在一个C的子集U中进行分析；而在上近似分析中，则会在一个C的超集O中进行分析。  
为了保证分析的正确性（Soundness），下近似分析一般只用于找错（证伪，Falsification），但无法用于证明（Verification）。这是因为，在实际状态集C的子集U中寻找到的可达错误状态，一定也是C中的可达错误状态。反之，U中不存在可达错误状态却不能说明C中亦不存在可达错误状态。软件测试可以视为一种下近似分析；
上近似分析则一般只用于证明，而不直接用于找错。这是因为在实际状态集C的超集O中不存在可达的错误状态，那么C中一定也不存在可达错误状态。反之，O中存在可达的错误状态，却不能说明C中亦存在可达的错误状态。一般基于抽象的方法，比如静态分析中的各类基于抽象解释的分析算法，程序验证中的谓词抽象、路径抽象等等，都是上近似分析；引入不变式也是一种上近似。  
instead of the concrete post, we compute an abstract post post#  
```
Abstract Post:

Consider the following formula φ ≙ (∀x.∀y. (x>0 ∧ f(x)=y) → y>x)) ∧ z≥4 .

We want to compute the abstract postcondition post#(φ, z) with respect to predicates P ≙ {z≥0, z≤0, z≥5, f(z)≥5}.

Which of the following statements is true?

  The abstract post condition is f(z)≥5. 
  The abstract post condition is z≥0. 
  The abstract post condition is z≤0. 
 
  The abstract post condition is z≥0 ∧ f(z)≥5.  Correct!
```
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

```
Non-interference:

Consider the following program s, where only obs can be observed by an attacker.  

x := secret;
if (x>=0){ obs:= 2;}
obs:=0;
The program satisfies non-interference, but there exists no Γ, such that Γ(obs)=obs, Γ(secret)=sec and Γ, obs ⊢ s, i.e., there is no Γ such that s type-checks, using our IFC type system.
```

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
```
Information Flow Control:

You're a newly hired security engineer. The company you work in consists of four employees, alice, bob, greg, and dave, whose relationship is characterized by a lattice, where the following relations hold:

bob ⊑ alice
dave ⊑ alice
greg ⊑ bob
greg ⊑ dave

In particular, it's not the case that bob ⊑ dave or dave ⊑ bob.

Your task is to check the local software for leaks. Let's assume you're given the typing environment

Γ(x)= alice, Γ(y)=bob, Γ(z)=dave, and Γ(q)=greg, and the following three programs:

(1) x := y+z

(2) z := y+1

(3) q := y+z

We're interested in whether these programs type check with pc label greg. Which of the following statements is true?


  Program (1), type checks, but not programs (2) and (3).  Correct!
```

### Explicit flows and side channels
<img width="697" alt="image" src="https://github.com/zhang-mickey/logic/assets/145342600/04b3eb53-7b29-4405-ae73-ad463f63518a">

### time attack
In cryptography, a timing attack is a `side-channel attack` in which the attacker attempts to compromise a cryptosystem by analyzing the time taken to execute cryptographic algorithms. Every logical operation in a computer takes time to execute, and the time can differ based on the input; with precise measurements of the time for each operation, an attacker can work backwards to the input.

## Security type system(language-based security)
An alternative approach for non-interference  
For statement s, if s is well-typed, then s should be non-interferent.  
In a programming language augmented with a security type system every expression carries both a type (such as boolean, or integer) and a security label.
### type statement
Skip is always well-typed.  

### Program counter label
pc tracks the security label of the program counter  
if we are in an if-statement or loop that depends on a sec variable, the pc label is sec.  
If we assign to a variable, we need to check it is at least as confidential as the program counter.  
## Speculative Execution

# literature
程序分析与验证中的近似思想  

The formal semantics of programming languages  

https://github.com/barghouthi/cs704  
https://theory.stanford.edu/~arbrad/slides/  
Hoare logic:  
https://www.cl.cam.ac.uk/teaching/2021/HLog+ModC/slides/  
https://cmu-program-analysis.github.io/2023/index.html
