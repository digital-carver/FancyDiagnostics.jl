# FancyDiagnostics - Enhance your Julia error message experience

[![Build Status](https://travis-ci.org/Keno/FancyDiagnostics.jl.svg?branch=master)](https://travis-ci.org/Keno/FancyDiagnostics.jl)

[![Coverage Status](https://coveralls.io/repos/Keno/FancyDiagnostics.jl/badge.svg?branch=master&service=github)](https://coveralls.io/github/Keno/FancyDiagnostics.jl?branch=master)

[![codecov.io](http://codecov.io/github/Keno/FancyDiagnostics.jl/coverage.svg?branch=master)](http://codecov.io/github/Keno/FancyDiagnostics.jl?branch=master)

FancyDiagnostics replaces the standard julia parsing mechanics and substitues in [CSTParser](https://github.com/ZacLN/CSTParser.jl).
CSTParser provides a richer set of diagnostics than the base julia parser. This package
allows you to take advantage of that in the REPL. Please note however, that CSTParser does not currently
have the same level of maturity as the base parser. Please file an issue on CSTParser if you encounter
a syntax construct that gets parsed incorrectly after loading this package.

# Usage

After installing the package, simply place

```julia
using FancyDiagnostics
```

in your .juliarc.jl.

# Example

Before:

```julia
julia> a && && b
ERROR: syntax: invalid identifier name "&&"
```

After:

```julia
REPL[1]:1:6 ERROR: Unexpected operator
a && && c
     ^~~
```