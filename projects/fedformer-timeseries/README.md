# FEDformer Time-series Adaptation

Goal: adapt an ETT-oriented FEDformer pipeline to a custom pickle dataset.

Key issues: dataset path/read method mismatches, missing `__read_data__`, shape conflicts between trend and residual tensors, and output-channel projection mismatches.
