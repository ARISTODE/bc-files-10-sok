LLVM bitcode files for Linux drivers built with LLVM/Clang 10.0.0.

This repository is organized with plain folders, not Git submodules.

Layout:

- `linux-drivers/`: exact 10.0.0 bitcode copied from `linux/drivers`,
  preserving the kernel driver subsystem layout, for example `acpi/`, `gpu/`,
  `net/`, `usb/`, `tty/`, and so on.
- `sound/`, `i2c/`, `msr/`, `null_blk/`, etc.: paired module bitcode copied
  from the local `bc-files` dataset.
- `arch_x86/msr/`: original driver-only `msr.ko.bc` artifact from this
  repository.

The paired driver directories contain both:

- `*.ko.bc`: driver/module bitcode
- `*_kernel.bc`: corresponding kernel-side bitcode

Some directories also include additional 10.0.0 bitcode artifacts such as
`*.bc` and `*_nescheck.bc`.

`MANIFEST.tsv` records each bitcode file, its source path, SHA-256 digest, and
the detected 10.0.0 compiler marker.

Current contents:

- 1,149 exact LLVM/Clang 10.0.0 `.bc` files
- 1,101 driver object bitcode files (`*.o.bc`) from `linux/drivers`
- 19 driver/module bitcode files (`*.ko.bc`)
- 16 kernel-side paired bitcode files (`*_kernel.bc`)
- 13 additional module/checker bitcode files

Note: exact LLVM 10.0.0 kernel counterparts for the `alx` and `ixgbe` module
artifacts were not present in the local datasets. Their exact 10.0.0 driver
artifacts are included under `linux-drivers/net/ethernet/...`.
