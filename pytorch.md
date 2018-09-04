# Pytorch

## Detach and clone

https://discuss.pytorch.org/t/clone-and-detach-in-v0-4-0/16861\

> 1. `tensor.detach()` creates a tensor that shares storage with `tensor` that does not require grad. `tensor.clone()`creates a copy of tensor that imitates the original `tensor`'s `requires_grad` field. You should use `detach()` when attempting to remove a tensor from a computation graph, and `clone`as a way to copy the tensor while still keeping the copy as a part of the computation graph it came from.
> 2. `tensor.data` returns a new tensor that shares storage with `tensor`. However, it always has `requires_grad=False` \(even if the original `tensor` had `requires_grad=True`
> 3. You should try not to call `tensor.data` in 0.4.0. What are your use cases for `tensor.data`?
> 4. `tensor.clone()` makes a copy of `tensor`. `variable.clone()` and `variable.detach()` in 0.3.1 act the same as `tensor.clone()` and `tensor.detach()` in 0.4.0.

| Item | detach | clone | data |
| :--- | :--- | :--- | :--- |
| requires\_grad | False | Same as origin tensor \(??\) | False |
| note |  |  | Not use in 0.4.0 |

## Retain graph

https://discuss.pytorch.org/t/runtimeerror-trying-to-backward-through-the-graph-a-second-time-but-the-buffers-have-already-been-freed-specify-retain-graph-true-when-calling-backward-the-first-time/6795



