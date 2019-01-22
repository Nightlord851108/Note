# Binary Relation
## Reflexive
For all x in X it holds that xRx. For example, "greater than or equal to" (≥) is a reflexive relation but "greater than" (>) is not.
## Irreflexive
For all x in X it holds that not xRx. For example, > is an irreflexive relation, but ≥ is not.
## Coreflexive
For all x and y in X it holds that if xRy then x = y.
## Symmetric
For all x and y in X, it holds that if xRy, then yRx
## Antisymmetric
For all x and y in X, it holds that if xRy and yRx, then x = y. For example, ≥ is anti-symmetric; so is >, but vacuously (the condition in the definition is always false).
## Asymmetric
For all x and y in X, it holds that if xRy, then **not** yRx. For example, > is asymmetric, but ≥ is not.
## Transitive relation
For all x, y and z in X it holds that if xRy and yRz then xRz. For example, "is ancestor of" is transitive, while "is parent of" is not.
Let A be a set in which the relation R defined.

R is said to be transitive, if

(a, b) ∈ R and (b, a) ∈ R ⇒ (a, c) ∈ R,

That is aRb and bRc ⇒ aRc where a, b, c ∈ A.

The relation is said to be non-transitive, if

(a, b) ∈ R and (b, c) ∈ R do not imply (a, c ) ∈ R.

### Question: Is the following statement tru? "For all transitive relations, if S and R are transitive relations, then S∪R is transitive."
**Ans: False.**
Suppose (x,y) is in R, and (y,z) is in S, but (x,z) is in neither.

Then R and S could both be transitive, but  their union wouldn't be, because it would be missing (x, z).

So you can't prove that the union of two transitive relations is also transitive, because it is not always true.

If ⟨x,y⟩ and ⟨y,z⟩ belong to R∩S, then both belong to R, so you can apply transitivity of R, and both belong to S, so you can apply transitivity of S. Thus, you get ⟨x,z⟩ in both R and S and therefore in they’re intersection

## connex
for all x and y in X it holds that xRy or yRx (or both). This property is sometimes called "total", which is distinct from the definitions of "total" given in the previous section.
