# Constants

[![Build Status](https://travis-ci.org/Roger-luo/Constants.jl.svg?branch=master)](https://travis-ci.org/Roger-luo/Constants.jl)

[![Coverage Status](https://coveralls.io/repos/Roger-luo/Constants.jl/badge.svg?branch=master&service=github)](https://coveralls.io/github/Roger-luo/Constants.jl?branch=master)

[![codecov.io](http://codecov.io/github/Roger-luo/Constants.jl/coverage.svg?branch=master)](http://codecov.io/github/Roger-luo/Constants.jl?branch=master)

Some useful constants for Julia.


# Usage

Use import to import certain constant's alias input the scope. And you can access some property by the following commands.

```julia-repl
# import atomic unit of charge
julia> import Constants: e

julia> e.quantity
"atomic unit of charge"

julia> e.uncertainty
9.8e-28

julia> e.unit
"C"

julia> e.value
1.6021766208e-19

```

All the constants overload most of the interface of `Number` and constant types are subtypes of `Number`. Therefore, you can just use them like native numbers

```julia-repl
julia> e * 2
3.2043532416e-19

julia> e + 2
2.0

```

# A list of included constants

All constants is stored in a `Dict` called `DATA`, `Constants` will `export` this dict, you can access it by

```julia-repl
julia> import Constants

julia> Constants.DATA
```

or 

```julia-repl
julia> using Constants

julia> DATA
```

### NIST CODATA Fundamental Physical Constants

`Constants` will download a JSON file from [NIST CODATA]("https://nist.gov/srd/srd_data//srd121_allascii_2014.json") automatically when you install the package. All constants in this JSON file is included. This part can be access from `DATA` by

```julia-repl
julia> Constants.DATA["NIST"]["YOUR CONSTANT NAME"]
```

e.g

```julia-repl
julia> Constants.DATA["NIST"]["standard atmosphere"]
101325.0

```

### Defined Constants

Some constants is defined in theory, like **magnetic constant (vacuum permeability)**, they are also supported, currently we have:

### List of Bindings

- `c`: speed of light in vacuum
- `c0`: speed of light in vacuum
- `G`: Newtonian constant of gravitation
- `g`: standard acceleration of gravity
- `h`: Planck constant
- `ħ` : Planck constant over 2 pi
- `e`: atomic unit of charge (use `eu` for mathematical constant `e`)
- `a0` : Bohr radius
- `α` : fine-structure constant
- `k`: Boltzmann constant
- `NA`: Avogadro constant
- `atm`: standard atmosphere
- `μ0`: magnetic constant (vacuum permeability)
- `ε0`: electric constant (vacuum permittivity)
