LLVM bitcode files for Linux drivers built with LLVM/Clang 10.0.0.

The paired driver directories in this repository contain both:

- `*.ko.bc`: driver/module bitcode
- `*_kernel.bc`: corresponding kernel-side bitcode

Some directories also include additional 10.0.0 bitcode artifacts such as
`*.bc` and `*_nescheck.bc`.

`MANIFEST.tsv` records each bitcode file, its source path, SHA-256 digest, and
the detected 10.0.0 compiler marker.

Note: the top-level `alx.ko.bc`, `ixgbe.ko.bc`, and `msr.ko.bc` files are the
original driver-only artifacts from this repository. Exact LLVM 10.0.0 kernel
counterparts for `alx` and `ixgbe` were not present in the local datasets; `msr`
has a paired copy under `msr/`.
