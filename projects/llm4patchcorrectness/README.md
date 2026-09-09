# LLM4PatchCorrectness / CodeBLEU Verifier

Goal: evaluate APR patch correctness with LLM-based and similarity-based methods.

A Windows CPU-only setup required removing CUDA-specific calls and DataParallel assumptions.

Custom verifier combined n-gram, syntax, and semantic similarity. Evaluation focuses on Accuracy, F1, AUC, and logit-label alignment.
