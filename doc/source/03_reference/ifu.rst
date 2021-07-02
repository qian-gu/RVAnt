.. _ifu:

Instruction Fetch Unit
=======================

IFU(Instruction Fetch Unit) read instructions from outside memory, and send instructions to next stage at the speed of 1 instr/cycle if the memory is ``ITCM`` whose latency is 1 cycle.

Misalign Access
---------------

Because RVAnt does NOT support **C** extension, so there are no align problems.

Local Instruction buffer
-------------------------

Considering RVAnt is a minimal MCU core for low power application, the core is intergrated with a ``ITCM``, so it's has no necessary to include a instruction FIFO or buffer in IFU.

Branch Predicition
-------------------

The main function of IFU is to predict the next ``PC`` according current instruction. RVAnt adopts the most basic ``BTFN`` (backward taken, forward not taken) algorithm to simplify hardware design and optimize the area.

Memory Interface
----------------------

The ITCM and DTCM follow the same protocal called ``RMI`` (RVAnt Memory Interface), which is divide into 2 channel: request channle and response channel.

.. wavedrom::
   :align: center

    {"signal":
    [
        {"name": "clk", "wave": "p........"},
        {"name": "req", "wave": "01.0....."},
        {"name": "ack", "wave": "0.0000001000"}
    ]
    }

    