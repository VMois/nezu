# Nezu

Simple programming language developed using LLVM.
Based on [LLVM: My First Language Frontend](https://llvm.org/docs/tutorial/MyFirstLanguageFrontend/index.html).

```python
# Compute the x'th fibonacci number.
def fib(x)
  if x < 3 then
    1
  else
    fib(x-1)+fib(x-2)

# This expression will compute the 40th number.
fib(40)

# using external functions
extern sin(arg);
extern cos(arg);
extern atan2(arg1 arg2);

atan2(sin(.4), cos(42))
```

## How to develop

1. Start a docker container with LLVM intalled in the directory with `Nezu` code:

```bash
$ docker run --rm -v $PWD:/pwd --name llvm -it silkeh/clang:14 bash
```

2. Compile `nezu` binary:

```bash
clang++ -g -O3 nezu.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core` -o nezu
```

## Resources

[LLVM language reference](https://llvm.org/docs/LangRef.html)
