# NamedTensor

NamedTensor is a library for writing numpy / torch applications. The library has three strong opinions:

1) **View / transpose / broadcasting are too hard.**

    After writing tens of thousands of LoC in this style, I still constantly make dimensionality mistakes. 
    At best these are caught at runtime, at worst they lead to nasty bugs since this difference between 
    beautiful broadcasting and untraceable errors is often one transpose.

2) **Einsum is a flawed solution**

    The recent move to einsum is excellent and leads to both more readable and more concise code. 
    However, einsum fundamentally breaks abstraction, by requiring that all functions be aware of all 
    dimensions of a tensor. This leads to less general code. 

3) **Tensor code should have aggressive, dynamic checks**

    Since many applications are bottlenecked by internal matrix operations, 
    there is no excuse not to have extensive pre- and post-condition checks in dynamic code. 
    However in practice these quickly go out of date and out-of-sync with docs. 

## Proposal

This library represents a beta proposal for a named tensor for numpy/torch. The theory is that 
many of the problems above are simply consequences of defaulting to math-style tuple notation. Switching to 
struct-like notation can let us build abstractions on top of this library. 


> 


## Install

> pip install namedtensor

## 
