Getting Started
---------------

Please follow the instructions provided by the instructor to start your
lab and access your jump host.

.. NOTE::
	 All work for this lab will be performed exclusively from the 
	 jumphost. No installation or interaction with your local system is
	 required. RDP to Jumpbox f5student/f5DEMOs4u For Mac use Remote Desktop 10.X

Use Blueprint Terraform-f5-bp-0808
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Lab Topology
~~~~~~~~~~~~

The following components have been included in your lab environment:

- 1 x F5 BIG-IP VE (v13.1)
- 1 x Webserver (xubuntu 14.04)
- 1 x Jumphost  

  .. image:: /_static/topo.png

Lab Components
^^^^^^^^^^^^^^


The following table lists VLANS, IP Addresses and Credentials for all
components:

.. list-table::
    :widths: 20 40 40
    :header-rows: 1
    :stub-columns: 1

    * - **Component**
      - **VLAN/IP Address(es)**
      - **Credentials**
    * - Jump Box use RDP
      - - **Management:** 10.1.1.10
        - **External:** 10.1.10.51
      - ``f5student``/``f5DEMOs4u``

.. list-table::
    :widths: 20 40 40
    :header-rows: 1
    :stub-columns: 1

    * - **Component**
      - **VLAN/IP Address(es)**
      - **Credentials**
    * - BIG-IP Access 
      - - **Management:** https://10.1.1.246
        - **External:** 10.1.10.246
        - **Internal:** 10.1.20.246
      - ``admin``/``admin``

    
