# About
The docker-compose starts a simplified version of Nussknacker Request-Response processing mode - this version does not require Kubernetes. 
Please browse through basic terminology used in this readme (component, scenario, engine, node): https://nussknacker.io/documentation/about/GLOSSARY/

# Prerequisites
- Ubuntu
- docker
- docker-compose

# Startup command
	docker-compose up # from the directory where the docker-compose.yml file is located

# Additional configuration
	
Enrichers configuration should be added to app.conf; if you do it correctly, you will them in the components pallette. 

# Steps

- start the containers using the startup command
    - open Designer UI in the browser on localhost:8180
    - id / password is admin / admin
- you will see main window with empty list of scenarios
    - click create to add a new scenario, give it a name of yourName, leave the category unchanged
- use the right panel to perform the following actions:
    - import scenario helloWorld-4.json
    - inspect scenario properties - you will find the input and output schemas there. If you used streaming engine, the schemas would be kept in the Schema Registry
    - click save, you can leave comment blank
    - deploy scenario, you can leave comment blank
- call the scenario from the command line 
     
     `curl localhost:8183/scenario/plk   -HContent-Type:application/json -d '{"data1": "in Nu Request - Response embedded processing mode", "data2":123}'`
- check the OpenAPI service definition 

    `curl localhost:8183/scenario/plk/definition` 



# Further reading:
- https://nussknacker.io/documentation/docs/scenarios_authoring/Intro/
- https://nussknacker.io/documentation/docs/scenarios_authoring/RRDataSourcesAndSinks/







