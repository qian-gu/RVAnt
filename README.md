# RVAnt :ant:

[![Build Status]()]()
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg?style=flat-square)](https://conventionalcommits.org)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?style=flat-square&logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

RVAnt is a minimal implementation of RV32I written in SystemVerilog for individual study purpose.

## Table of Contents

- [RVAnt :ant:](#rvant-ant)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Microarchitecture](#microarchitecture)
  - [Performance](#performance)
  - [Directory Description](#directory-description)
  - [Build and Test](#build-and-test)
  - [Documents](#documents)
  - [Contributing](#contributing)

## Features

- RV32I[M]_Zicsr_Zifencei
- M-mode only
- 3-stage pipeline
- in-order single issue
- out-of-order execution
- writen in SystemVerilog
- MIT license

## Microarchitecture

The microarchitecture of RVAnt:

![march](doc/source/_static/rvant_march.svg)

## Performance

## Directory Description

| Module                | Description                                                           |
| --------------------- | --------------------------------------------------------------------- |
| `rvant`               | The RVAnt CPU                                                         |
| `rvant_axi`           | The version of the CPU with AXI4-Lite interface                       |
| `rvant_axi_adapter`   | Adapter from PicoRV32 Memory Interface to AXI4-Lite                   |
| `rvant_wb`            | The version of the CPU with Wishbone Master interface                 |
| `rvant_pcpi_mul`      | A PCPI core that implements the `MUL[H[SU\|U]]` instructions          |
| `rvant_pcpi_fast_mul` | A version of `picorv32_pcpi_fast_mul` using a single cycle multiplier |
| `rvant_pcpi_div`      | A PCPI core that implements the `DIV[U]/REM[U]` instructions          |

## Build and Test

## Documents

You can build the documents on your local machine using sphinx,

```bash
cd doc
pip3 install -r requirements.txt
make clean
make html
```

or read the [online documents]().

## Contributing

Check out [LowRISC Style Guide](https://github.com/lowRISC/style-guides/blob/master/VerilogCodingStyle.md). Follow the [conventional Commits](https://www.conventionalcommits.org), it's recommanded to use [commitizen](https://github.com/commitizen-tools/commitizen) with [pre-commit](https://pre-commit.com/) enabled.

```bash
# install Commitizen
pip3 install -r requirements.txt
pre-commit install --hook-type commit-msg
```
