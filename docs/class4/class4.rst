Create Simple VS, Pool etc using bigip terraform resources
----------------------------------------------------------

Please follow the instructions provided by the instructor to start your
lab and access your jump host.

This class covers the following topics:

- Update the master.tf file to include Infra structure resources like NTP, DNS, VLAN
- Update master.tf file to include Application Objects like Virtual Server, Pool, nodes etc.
- Execute Terraform Plan to check what terraform will create on big-ip 
- Execute Terraform apply to manifest the configuration on big-ip 

#. Open master.tf in  terminal on the Client/Jumpbox VM   

		provider "bigip" {

			address = "10.1.1.246"

			username = "admin"

			password = "admin"

		}
 
#. Update master file to include ntp resource   

		resource "bigip_sys_ntp" "ntp1" {

			description = "/Common/NTP1"

			servers = ["time.google.com"]

			timezone = "America/Los_Angeles"

		}

		resource "bigip_sys_dns" "dns1" {

			description = "/Common/DNS1"

			name_servers = ["8.8.8.8"]

			number_of_dots = 2

			search = ["f5.com"]

		}
		resource "bigip_net_vlan" "vlan1" {

			name = "/Common/internal"

			tag = 101

			interfaces = {

				vlanport = 1.2,

				tagged = false

			}	

		}

		resource "bigip_net_vlan" "vlan2" {

				name = "/Common/external"

				tag = 102

				interfaces = {

						vlanport = 1.1,

						tagged = false

				}

		}

		resource "bigip_net_selfip" "selfip1" {

			name = "/Common/internalselfIP"

			ip = "10.1.20.246/24"

			vlan = "/Common/internal"

			depends_on = ["bigip_net_vlan.vlan1"]

			}

		resource "bigip_net_selfip" "selfip2" {
		
				name = "/Common/externalselfIP"
		
				ip = "10.1.10.246/24"
		
				vlan = "/Common/external"
		
				depends_on = ["bigip_net_vlan.vlan2"]
		
				}


		resource "bigip_ltm_monitor" "monitor" {
		
				name = "/Common/terraform_monitor"
		
				parent = "/Common/http"
		
				send = "GET /some/path\r\n"
		
				timeout = "999"
		
				interval = "999"
		
		}

		resource "bigip_ltm_pool"  "pool" {
		
				name = "/Common/terraform-pool"
		
				load_balancing_mode = "round-robin"
		
				monitors = ["/Common/terraform_monitor"]
		
				allow_snat = "yes"
		
				allow_nat = "yes"
		
		}

		resource "bigip_ltm_pool_attachment" "attach_node" {
		
				pool = "/Common/terraform-pool"

		  		node = "/Common/10.1.20.251:80"

				depends_on = ["bigip_ltm_pool.pool"]

		}
		resource "bigip_ltm_virtual_server" "http" {
	
				pool = "/Common/terraform-pool"
	
				name = "/Common/terraform_vs_http"
		
				destination = "10.1.10.100"
			
				port = 80
				
				source_address_translation = "automap"
				
				depends_on = ["bigip_ltm_pool.pool"]
	
		}

.. NOTE::
	 All work for this lab will be performed exclusively from the Windows
	 jumphost. No installation or interaction with your local system is
	 required.
