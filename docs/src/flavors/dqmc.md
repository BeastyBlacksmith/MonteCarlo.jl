# Determinant Quantum Monte Carlo (DQMC)

This is determinant quantum Monte Carlo (MC) also known auxiliary field quantum Monte Carlo. It can be used to simulate interacting fermion systems, here the auxiliary boson arises from a Hubbard Stratonovich transformation, or fermions which are naturally coupled to bosons. An example is the [Attractive Hubbard Model](@ref).

You can initialize a determinant quantum Monte Carlo simulation of a given `model` simply through
```julia
dqmc = DQMC(model, beta=5.0)
```

Mandatory keywords are:

* `beta`: inverse temperature

Allowed keywords are:

* `delta_tau::Float64 = 0.1`: imaginary time step size
* `safe_mult::Int = 10`: stabilize Green's function calculations every `safe_mult` step (How many slice matrices can be multiplied until singular value information is lost due to numerical unaccuracy?)
* `sweeps`: number of measurement sweeps
* `thermalization`: number of thermalization (warmup) sweeps
* `seed`: initialize DQMC with custom seed
* `all_checks::Bool = true`: turn off to suppress some numerical checks


Afterwards, you can run the simulation by
```julia
run!(dqmc)
```

## Checkerboard decomposition

Mention generic checkerboard defined in `flavors/DQMC/abstract.jl`. When is a lattice compatible with the general decomposition? Manual implementation of `build_checkerboard`.

## Technical details

imaginary time slice matrices $B_l = e^{-\Delta\tau T_{ij}/2} e^{-\Delta\tau V_{ij}(l)} e^{-\Delta\tau T_{ij}/2}$ and more importantly the equal-time Green's function $G = \left( 1 + B_M \cdots B_1 \right)^{-1}$

### Symmetric Suzuki-Trotter decomposition

We use the symmetric version of the Suzuki-Trotter decomposition, i.e.

TODO!

### Effective slice matrices and Green's function

TODO! Important!

## Exports

```@autodocs
Modules = [MonteCarlo]
Private = false
Order   = [:function, :type]
Pages = ["DQMC.jl"]
```

## Potential extensions

Pull requests are very much welcome!

 * todo