# Supporting Mask R-CNN on Google Cloud TPU with PyTorch

> **Author**: Aurélien Bombo<br>
> **Date**: December 9, 2019<br>
> **NOMA**: 3025-15-00

During my fall internship at Google in Seattle (from Oct 14 to Dec 20),
I have been tasked with researching and implementing support for the [Mask R-CNN][mask_rcnn]
model on [Google Cloud TPU][cloud_tpu] with [PyTorch][pytorch].

## What?

**Mask R-CNN** is a state-of-the-art computer vision technique for instance
segmentation. It uses region-based convolutional neural networks to output a
contour for each object detected in an image, rather than merely bounding boxes.
Here are some examples from the original paper:

![](https://miro.medium.com/max/4000/1*lMEd6AcDmpH0mDzBHyiERw.png)

**Google Cloud TPU** is a service that allows developers to deploy their
deep learning models in the cloud and run them on the TensorFlow Processing Unit
(TPU). The TPU is a chip specifically developed by Google to accelerate
matrix-heavy computation workloads. This lets developers train and test their
models much more quickly and at much less expense than with GPUs.

Finally, **PyTorch** is an open source deep learning Python library developed by Facebook.
It is generic in that it allows implementing virtually any kind of deep learning
model, and it is a competitor of Google's TensorFlow library.

## Why?

As mentioned previously, Mask R-CNN is a state-of-the-art model and it achieves
better performance than its predecessor Faster R-CNN, at a greater speed.
With Google and Facebook announcing [support for PyTorch 1.3 on Cloud TPU][pytorch_tpu_blog]
back in October, it is crucial to actually be able to show off Cloud TPU's
capabilities.

## Problem and solution

The initial problem at hand pertains to limitations of the PyTorch/TPU runtime.

The repo that implements the meat of the support for TPUs in PyTorch lives at
[pytorch/xla](https://github.com/pytorch/xla). This repo is contributed to by
both Google and Facebook, and essentially implements a JIT compiler for Python
code to be run on TPUs. The need for a compiler stems from the fact that the
TPU runtime executes a compiled computation graph where nodes represent operations
while edges represent data (tensors) flowing between those operations.

The issue, however, is that PyTorch/XLA does not support dynamic shapes; meaning
it will trigger a recompilation of the graph every time a given tensor's shape is
mutated. As a concrete example: for Mask R-CNN, since the number of objects in
image A is different from image B, the shape of the tensor containing the bounding
boxes changes at each iteration and is thus dynamic. Problem is, recompilations
are extremely time-consuming and completely annihilate the speed advantage gained
from TPUs.

A solution is to modify the implementation of the model to make its behavior
static, and thus avoid recompilations, while ensuring that the output of the model
stays coherent. The reference PyTorch implementation of the model lives in the
[pytorch/vision][pytorch_vision] repo.

## What have I done so far?

The first few weeks of my internship were mostly dedicated to researching and
learning, as deep learning, Mask R-CNN, PyTorch, and Cloud TPU were all new to me.

In the first week, I submitted 1 merged PR containing 2 commits addressing
lack of clarity in the documentation, as well as fixing a buggy code example:
https://github.com/pytorch/xla/pull/1209.

Then I started taking over the initial work done by my manager at Google, and
forked [his repo](manager_repo) (which he had himself forked off pytorch/vision).

Since his last commit occurred back in June and development happens extremely
quickly in the upstream repo, his code was not compatible with pytorch/xla anymore
(pytorch/vision and pytorch/xla are somewhat coupled). Therefore, in a
[first PR][merge_pr], I merged upstream into his work and resolved the many
conflicts that came up.

In a [second PR][2nd_pr], I actually implement some of the changes needed to
eliminate most dynamicity in Mask R-CNN. There is still more work to be done,
but the speed improvement so far is significant: **inference time per image is now
~1.4 sec instead of ~21 min**.

[mask_rcnn]: https://arxiv.org/abs/1703.06870
[cloud_tpu]: https://cloud.google.com/tpu/
[pytorch]: https://pytorch.org/
[pytorch_tpu_blog]: https://pytorch.org/blog/pytorch-1-dot-3-adds-mobile-privacy-quantization-and-named-tensors/
[pytorch_vision]: https://github.com/pytorch/vision
[manager_repo]: https://github.com/jysohn23/vision/tree/tpu_compat
[merge_pr]: https://github.com/jysohn23/vision/pull/2
[2nd_pr]: https://github.com/jysohn23/vision/pull/3
