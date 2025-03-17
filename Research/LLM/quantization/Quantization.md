# Quantization
## Basics
Reducing the precision of weights while trying to keep the model’s inference results as accurate as possible.
Works especially well for text generation, set of most likely next tokens is important and not the exact values of next token logit distribution.
Next token logit distribution stays roughly the same so that an argmax or topk operation gives the same results.
	
There are various quantization techniques.
In general, it works as follows:
1. Quantize all weights to the target precision
2. Load the quantized weights, and pass the input sequence of vectors in bfloat16 precision
3. Dynamically dequantize weights to bfloat16 to perform the computation with their input vectors in bfloat16 precision
	
bfloat16: model weights are typically stored in full-precision (fp32). Quantization involves half-precision (bf16) or even more reduced ones.

## Implementation	
Implemented with "bitsandbytes" library for Python.

Currently, requires [CUDA-based GPU](https://huggingface.co/docs/bitsandbytes/en/installation?backend=Intel%20CPU%20%2B%20GPU#multi-backend), but has experimental multiplatform version (though, Intel is supported only on Linux)