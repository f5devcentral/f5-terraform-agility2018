Build F5 BIG-IP Provider
------------------------

.. TODO:: Complete getting started instructions

Please follow the instructions provided by the instructor to start your
lab and access your jump host.

      
     ``go version``

     ``go versio``
     
	 ``go1.9.2 darwin/amd64``
     
	 ``cd``
     
	 ``mkdir workspace``
     
	 ``export GOPATH=$HOME/workspace``
     
	 ``mkdir -p $GOPATH/src/github.com/f5devcentral``
     
	 ``cd $GOPATH``
     
	 ``go get github.com/f5devcentral/terraform-provider-bigip``
     
	 ``cd src/github.com/f5devcentral/terraform-provider-bigip/``
     
	 ``go build``
     
	 ``create .tf``
     
	 ``terraform init``
     
	 ``Initializing provider plugins...``

       Terraform has been successfully initialized!

       You may now begin working with Terraform. Try running "terraform plan" to see
       any changes that are required for your infrastructure. All Terraform commands
       should now work.

       If you ever set or change modules or backend configuration for Terraform,
       rerun this command to reinitialize your working directory. If you forget, other
       commands will detect it and remind you to do so if necessary.``

.. NOTE::
	 All work for this lab will be performed exclusively from the Windows
	 jumphost. No installation or interaction with your local system is
	 required.
