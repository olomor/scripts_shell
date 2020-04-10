
# parse_yaml.sh


## Dummy test config file "zconfig.yml"

    development:
      adapter: mysql2
      encoding: utf8
      database: my_database
      username: root

## Test script:

    #!/bin/sh
    
    # include parse_yaml function
    . parse_yaml.sh
    
    # read yaml file
    eval $(parse_yaml zconfig.yml "config_")
    
    # access yaml content
    echo $config_development_database
   
 
## Returned environment variables:

    config_development_adapter="mysql2"
    config_development_encoding="utf8"
    config_development_database="my_database"
    config_development_username="root"

