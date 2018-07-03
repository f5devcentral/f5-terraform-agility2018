Lab – Download the GO tar file 
-----------------------------------
In this task you will open a web browser and navigate to the https://golang.org/dl/
site.

.. NOTE:: You don't need GO programming skills.

Follow these steps to complete this task:

#. Open your web browser
#. Navigate to https://golang.org/dl/

  .. image:: /_static/goimage.png

Task – Download the Go Package as shown in Above
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Follow these steps to complete this task:

#. Click on the Linux ``go1.10.3.linux-amd64.tar.gz`` file.

#. Open terminal on the Client/Jumpbox VM

#. Execute the following command on Jumpbox terminal

   ``cd Download``

   ``sudo tar -C /usr/local -xzf go1.10.3.linux-amd64.tar.gz``
   
   .. IMPORTANT:: Enter password as f5DEMOs4u and username f5student

#. Include GO executable in the Path

  ``export PATH=$PATH:/usr/local/go/bin``

#. Test GO pacakage by executing

  ``go version``
 
  .. IMPORTANT:: You should see the following

    ``go version go1.10.3 linux/amd64``
