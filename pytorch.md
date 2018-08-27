# Pytorch

## Detach and clone

{% embed data="{\"url\":\"https://discuss.pytorch.org/t/clone-and-detach-in-v0-4-0/16861\",\"type\":\"link\",\"title\":\"Clone and detach in v0.4.0\",\"description\":\"I’m currently migrating my old code from v0.3.1 to v0.4.0. During migration, I feel confused by the document about clone and detach. After searching related topics in the forum,  I find that most discussions are too old.  Specifically, I want an answer to the three following questions:   the difference between tensor.clone\(\) and tensor.detach\(\) in v0.4.0? the difference between tensor and tensor.data in v0.4.0? the difference between tensor and tensor.data when calling clone\(\) or detach\(\) in v0....\",\"icon\":{\"type\":\"icon\",\"url\":\"https://discuss.pytorch.org/uploads/default/original/2X/3/38d28fd067a1a8f263e14507942b2e38e49b771a.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://discuss.pytorch.org/uploads/default/original/2X/3/38d28fd067a1a8f263e14507942b2e38e49b771a.png\",\"width\":144,\"height\":144,\"aspectRatio\":1}}" %}

> 1. `tensor.detach()` creates a tensor that shares storage with `tensor` that does not require grad. `tensor.clone()`creates a copy of tensor that imitates the original `tensor`'s `requires_grad` field. You should use `detach()` when attempting to remove a tensor from a computation graph, and `clone`as a way to copy the tensor while still keeping the copy as a part of the computation graph it came from.
> 2. `tensor.data` returns a new tensor that shares storage with `tensor`. However, it always has `requires_grad=False` \(even if the original `tensor` had `requires_grad=True`
> 3. You should try not to call `tensor.data` in 0.4.0. What are your use cases for `tensor.data`?
> 4. `tensor.clone()` makes a copy of `tensor`. `variable.clone()` and `variable.detach()` in 0.3.1 act the same as `tensor.clone()` and `tensor.detach()` in 0.4.0.

| Item | detach | clone | data |
| :--- | :--- | :--- | :--- |
| requires\_grad | False | Same as origin tensor \(??\) | False |
| note |  |  | Not use in 0.4.0 |

## Retain graph

{% embed data="{\"url\":\"https://discuss.pytorch.org/t/runtimeerror-trying-to-backward-through-the-graph-a-second-time-but-the-buffers-have-already-been-freed-specify-retain-graph-true-when-calling-backward-the-first-time/6795\",\"type\":\"link\",\"title\":\"RuntimeError: Trying to backward through the graph a second time, but the buffers have already been freed. Specify retain\_graph=True when calling backward the first time\",\"description\":\"I keep running into this error:  RuntimeError: Trying to backward through the graph a second time, but the buffers have already been freed. Specify retain\_graph=True when calling backward the first time.  Can someone explain what this means?  Independent of the context of the problem, I don’t understand what the buffers are and what it means for them to be “freed”.  Context: In my case, it happens the second time I call loss.backward\(\), in a function: where the model’s function execute one step ...\",\"icon\":{\"type\":\"icon\",\"url\":\"https://discuss.pytorch.org/uploads/default/original/2X/3/38d28fd067a1a8f263e14507942b2e38e49b771a.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://discuss.pytorch.org/uploads/default/original/2X/3/38d28fd067a1a8f263e14507942b2e38e49b771a.png\",\"width\":144,\"height\":144,\"aspectRatio\":1}}" %}


