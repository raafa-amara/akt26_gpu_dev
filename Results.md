# Results

Executed on Google Colab with a Tesla T4 GPU (compute capability 7.5).
Built with `make sm=75` (the makefiles default to sm=80 for A100).
The full run is in `colab_run.ipynb`.

## 3-ger (4000 x 2000)

| Implementation | Time (us) | GFLOP/s | Error norm |
|---|---|---|---|
| Custom kernel | 271.496 | 58.933 | 4.44e-08 |
| cuBLAS SGER | 302.895 | 52.824 | 4.44e-08 |

TEST PASS, speedup 1.116x

## 4-gemm

| Size / batch | Custom (us) | cuBLAS (us) | Max fwd error | Speedup |
|---|---|---|---|---|
| 16 x 16, 1000 | 20.692 | 42.652 | 2.44e-08 | 2.061x |
| 32 x 32, 1000 | 150.471 | 116.696 | 1.34e-08 | 0.776x |

TEST PASS for both.