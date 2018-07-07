Create JSON Payload for HTTP
----------------------------

Please follow the instructions provided by the instructor to start your
lab and access your jump host.

#. Simple JSON payload for HTTP::
   

        {
        "sample_01": {
        "b1": {
            "class": "Application",
            "serviceMain": {
                "class": "Service_HTTP",
                "pool": "web_pool",
                "virtualAddresses": [
                    "198.19.192.1"
                ]
         },
            "template": "http",
            "web_pool": {
                "class": "Pool",
                "members": [
                    {
                        "serverAddresses": [
                            "198.19.192.2",
                            "198.19.192.3"
                        ],
                        "servicePort": 80
                    }
                ],
                "monitors": [
                    "http"
                ]
            }
        },
        "class": "Tenant",
        "verifiers": {
            "13.x": "5ca2b95339f48129a0837952d3bdce2358a40c8339610ffd84866b2ff86351b5"
        }
        },
        "class": "ADC",
        "controls": {
        "archiveTimestamp": "2018-04-26T17:40:15.804Z"
        },
        "ident": "1524764414532",
        "schema_version": "3.0.0",
        "update_mode": "selective"
        }  


.. NOTE::
	 All work for this lab will be performed exclusively from the Windows
	 jumphost. No installation or interaction with your local system is
	 required.
