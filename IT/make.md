---
name: make
---

# make and Makefile

- <https://makefiletutorial.com/>

## Example

```Makefile
ARGS=-O3

all: build test

build:
    zig cc main.c $(ARGS) -o main.out

test:
    ./main.out
```

## Usage

```sh
make
# will do the first entry so "make all"

make all
# will do first "make build" then "make test"
make build
# will do the zig compilation
make test
# will launch the program
```

## Override variables

```sh
make ARGS=
make ARGS=-O2
```
