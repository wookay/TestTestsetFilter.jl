# TestTestsetFilter.jl

 - test/Project.toml
```toml
[deps]
Test = "8dfed614-e22c-5e08-85e1-65c5234f0b40"
Jive = "ba5e3d4b-8524-549f-bc71-e76ad9e9deed"

[targets]
test = ["Test", "Jive"]

[compat]
Jive = "0.2"
```

  - test/runtests.jl
```julia
using Jive
runtests(@__DIR__, testset="hello")

runtests(@__DIR__, testset=r"llo$")
```

  - test/test1.jl
```julia
using Test

@testset "hello" begin
@test true
end

@testset "world" begin
@test false
end
```


```shell
~/.julia/dev/TestTestsetFilter/test $  julia runtests.jl
1/1 test1.jl
    Pass: 1  (compile: 0.44, elapsed: 0.48 seconds)
✅  All 1 test has been completed.  (compile: 0.44, elapsed: 0.48 seconds)
1/1 test1.jl
    Pass: 1  (compile: 0.00, elapsed: 0.02 seconds)
✅  All 1 test has been completed.  (compile: 0.00, elapsed: 0.02 seconds)
```
