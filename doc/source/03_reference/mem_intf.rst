.. _mem-intf:

Memory Interface
==================

RVAnt is a minimal core for low power application, there are not any cache rather than ``ITCM`` and ``DTCM``. Both of the TCMs have the same interface called ``RMI`` (RVAnt Memory Interface), all the signal is listed in following table.

.. table:: RVAnt Memory Interface
   :align: center

   +----------+--------------+---------+----------------------------------+
   | Channel  | Signal       | Source  | Description                      |
   +==========+==============+=========+==================================+
   | Request  | ``req_vld``  | M       | request valid handshake          |
   |          +--------------+---------+----------------------------------+
   |          | ``req_rdy``  | S       | request ready handshake          |
   |          +--------------+---------+----------------------------------+
   |          | ``req_wr``   | M       | request write/read mode(1=write) |
   |          +--------------+---------+----------------------------------+
   |          | ``req_addr`` | M       | request address                  |
   |          +--------------+---------+----------------------------------+
   |          | ``req_wdat`` | M       | request write data               |
   |          +--------------+---------+----------------------------------+
   |          | ``req_wmsk`` | M       | request write mask               |
   +----------+--------------+---------+----------------------------------+
   | Response | ``rsp_vld``  | S       | response valid handshake         |
   |          +--------------+---------+----------------------------------+
   |          | ``rsp_rdy``  | M       | response ready handshake         |
   |          +--------------+---------+----------------------------------+
   |          | ``rsp_rdat`` | S       | response read data               |
   |          +--------------+---------+----------------------------------+
   |          | ``rsp_err``  | S       | response error                   |
   +----------+--------------+---------+----------------------------------+

The protocal is based on valid-ready handshake, example timing is showed in following diagrams.

.. wavedrom:: ../_static/rmi_read.json
   :caption: RMI Basic Back-to-Back Read Handshake
   :align: center

.. wavedrom:: ../_static/rmi_write.json
   :caption: RMI Basic Back-to-Back Write Handshake
   :align: center

Bus Interface Unit
===================