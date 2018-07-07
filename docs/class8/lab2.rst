Modify the master.tf file to include iapp resource
--------------------------------------------------

Please follow the instructions provided by the instructor to start your
lab and access your jump host.

#. Add iapp resource to use Simple http Json::
   

	resource "bigip_sys_iapp" "simplehttp" {
               name = "simplehttp"
               jsonefile = "${file("simplehttp.json")}"
               }





.. NOTE::
	 All work for this lab will be performed exclusively from the Windows
	 jumphost. No installation or interaction with your local system is
	 required.
