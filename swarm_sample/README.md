# swarm_sample

**create/start service**  
docker stack deploy -c docker-compose.yml getstartedlab

**check swarm cluster**  
http://aa00:8080/

**check the web**  
http://aa00/
http://aa01/
http://aa02/
http://aa03/

**common command**  
docker stack ls                                            # List stacks or apps  
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file  
docker service ls                 # List running services associated with an app  
docker service ps <service>                  # List tasks associated with an app  
docker stack ps  <service>                                    # as same as above  
docker inspect <task or container>                   # Inspect task or container  
docker container ls -q                                      # List container IDs  
docker stack rm <appname>                             # Tear down an application  
docker swarm leave --force      # Take down a single node swarm from the manager  
 
**push to docker hub**  
 #docker login
docker tag friendlyhello microsheen/get-started:part5
docker push microsheen/get-started:part5




 
