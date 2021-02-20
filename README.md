# PKG

## Goal

The main purpose is to create multiple independent packages while keeping maintainance costs at a minimum.

As observed in multiple projects it is advisable to use common `interfaces` for similar jobs, at the same time allow
different projects/users select their required implementation

## Structure

- The root folder **DOES NOT** have any specific modules or files. It is just a entrance for the modules. For some reason it is not possible to only have sub modules.
- All the modules should live inside their own folder and `go.mod`, `go.sum` files
- Modules should avoid, at all costs, interdependency. 

### Interface vs Implementation

It is advisable to split `interfaces` and implementation in different modules:

- `pkg/log`: keeps all `interface` and interface related methods
- `pkg/log/zap`: adds [`uber/zap`](https://go.uber.org/zap) implementation as a separated modules which uses `pkg/log` interfaces/methods.

This keeps all the related modules in a clear structure.


### TODO

- [] Example code for usage
- [] Unit tests
- [] Github actions (unit tests, release)
- [] Code coverage