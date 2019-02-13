# Master Method

## Formula
```
T(n) = aT(n/b) + f(n)
```
where we interpret n/b to mean either floor(n/b) or ceil(n/b). Then T(n) has the following asymptotic bounds.
1. If f(n) = O(n<sup>log<sub>b</sub>a-ε</sup>) for some constants ε > 0, then T(n) = Θ(n<sup>log<sub>b</sub>a</sup>).
2. If f(n) = Θ(n<sup>log<sub>b</sub>a</sup>), then T(n) = Θ(n<sup>log<sub>b</sub>a</sup>lg n).
3. If f(n) = Ω(n<sup>log<sub>b</sub>a+ε</sup>) for some constant ε > 0, and if af(n/b) ≤ cf(n) for some constant c < 1 and all sufficiently large n, then T(n) = Θ(f(n))
