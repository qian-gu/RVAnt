.. _overview:

RVAnt Overview
===============

RVAnt is a minial 32 bit RISC-V CPU core for learning purpose written in SystemVerilog.

Feature
----------

- RV32I[M]_Zicsr_Zifencei
- M-mode only
- 3-stage pipeline
- in-order single issue
- out-of-order execution
- writen in SystemVerilog
- MIT license

ISA Version
------------

.. table:: RVAnt Instruction Set Extension
   :align: center

   +-------------------------------------------------------------------+---------+-----------------+
   | Extension                                                         | Version | Configurability |
   +===================================================================+=========+=================+
   | **Zicsr**, Control and Status Register Instructions               |  2.0    |  always enable  |
   +-------------------------------------------------------------------+---------+-----------------+
   | **Zifencei**, Instruction-Fetch Fence                             |  2.0    |  always enable  |
   +-------------------------------------------------------------------+---------+-----------------+
   | **M**, Standard Extension for Integer Multiplication and Division |  2.0    |  optional       |
   +-------------------------------------------------------------------+---------+-----------------+

Performance
------------

Power
------------

Area
------------

License
------------

RVAnt is released under the **MIT license**, please see the ``LICENSE`` file for the full text.
