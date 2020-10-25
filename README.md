# spring cloud configuration server
- This is a test project represent cloud configuration server between many microservices to hold
each service configuration.
- This project read the configuration files for different services from git repository https://github.com/maboalim/microservice-config.git to be published to other services under port 8888
- The configuration files determine the stage of the application (dev, qc, prod, ...)

# Examples
URL examples:
http://localhost:8888/limits-service/dev
http://localhost:8888/limits-service/default
http://localhost:8888/currency-exchange-service/qc