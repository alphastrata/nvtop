# NVTOP

<center>

![img](assets/icon.jpeg)

An NVIDIA SMI'esk GPU Monitoring tool for your terminal.

</center>

### Contents:

- [usage](#Usage)
- [prerequisites](#prerequisites)
- [installation](#Installation)
- [why](#why)

`nvtop` is a command-line utility that provides a replacement for some of the output from `nvidia-smi` (System Management Interface).
It offers real-time monitoring and visualization of GPU information: Core Clock, Temps, Fanspeed and Memory Usage.

______________________________________________________________________

# Usage:

```
# Monitor the GPU and system with a 1-second update interval
nvtop --delay 1000
```

______________________________________________________________________

### Prerequisites

Before installing `nvtop`, ensure that you have Rust and Cargo (the Rust package manager) installed on your system. You can download and install Rust from the official website: [Rust Downloads](https://www.rust-lang.org/tools/install).

You will also need to at least confirm that `nvidia-smi` (The official NVIDIA tool that this one seeks to mimic) works.
_Why?_ Because, not all of the functionality from [`nvmlt-sys`](https://crates.io/crates/nvml-sys/versions) the library this app relies on does **not** guarantee all reporting functionality across ALL NVIDIA gpus.

## Installation

### Install from Git

You can install `nvtop` directly from the Git repository. Follow these steps:

1. Clone the `nvtop` repository to your local machine:

   ```bash
   git clone https://github.com/alphastrata/nvtop.git
   ```

1. Change to the `nvtop` directory:

   ```bash
   cd nvtop
   ```

1. Build and install `nvtop` using Cargo:

   ```bash
   cargo install --path .
   ```

### Install from Source

To install `nvtop` from the source code, you can follow these steps:

1. Download the source code or clone the repository to your local machine:

   ```bash
   git clone https://github.com/alphastrata/nvtop.git
   ```

1. Change to the `nvtop` directory:

   ```bash
   cd nvtop
   ```

1. Build the project using Cargo:

   ```bash
   cargo build --release
   ```

1. After building, you can find the `nvtop` executable in the `target/release/` directory.

### Install to Path

To make `nvtop` easily accessible from the command line, you can copy the executable to a directory in your system's `PATH`. For example, you can copy it to `/usr/local/bin`:

```bash
sudo cp target/release/nvtop /usr/local/bin/
```

Now, you can use `nvtop` from anywhere in your terminal.

______________________________________________________________________

# Why?

because \_this:

```shell
+---------------------------------------------------------------------------------------+
| NVIDIA-SMI 535.113.01             Driver Version: 535.113.01   CUDA Version: 12.2     |
|-----------------------------------------+----------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |         Memory-Usage | GPU-Util  Compute M. |
|                                         |                      |               MIG M. |
|=========================================+======================+======================|
|   0  NVIDIA TITAN RTX               Off | 00000000:0A:00.0  On |                  N/A |
| 41%   44C    P0              67W / 280W |   1367MiB / 24576MiB |      2%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+

+---------------------------------------------------------------------------------------+
| Processes:                                                                            |
|  GPU   GI   CI        PID   Type   Process name                            GPU Memory |
|        ID   ID                                                             Usage      |
|=======================================================================================|
|    0   N/A  N/A      1008      G   /usr/lib/Xorg                               439MiB |
+---------------------------------------------------------------------------------------+
```

is **boring**, and this:
![nvtop](assets/screenshot.png)

is **fun!**
