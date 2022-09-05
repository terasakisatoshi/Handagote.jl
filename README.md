# Handagote.jl

Experimental forward-mode AD library for tensor networks.

Hadagote = Handai + Zygote. This is because the library was created
when the author was in Handai (Osaka University) in Japan.

Compatible with OMEinsum.jl, Zygote.jl, etc.
The implementation is following HyperDualNumbers.jl.
https://github.com/JuliaDiff/HyperDualNumbers.jl

## TODO

* Dual Number operation
* supporting op(::Dual, ::HyperDual)
* supporting CUDA

## Einsum

In order to avoid type piracy, the functionality of OMEinsum.jl is duplicated.
Currently only supports the `@dualein_str` notation `dualein"ij, jk, klm -> ilm"(A, B, C)`,
and `@hyperdualein_str` notation `hyperdualein"ij, jk, klm -> ilm"(A, B, C)`.

## Bug

`similar(A, Dual{Float64}, (2, 3))` does not work. Use `similar(A, Dual{Float64}, 2, 3)`, instead.

## Future

Zygote over Handagote implementation of MPRG is a temporal ad-hoc solution.
In the future, we will change everything to Diffractor.jl backend.

## License

MIT

## Author

* Masahiko G. Yamada