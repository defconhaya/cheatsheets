
### Initializing a Swarm
1. **Initialize a Swarm**: 
   ```bash
   docker swarm init
   ```

2. **Join a Node to the Swarm**:
   On the manager node, run the command provided by `docker swarm init` on worker nodes to join them to the Swarm.

3. **Create a Swarm with Specific Advertise Address**:
   ```bash
   docker swarm init --advertise-addr <MANAGER-IP>
   ```

### Managing Nodes
4. **List Nodes**:
   ```bash
   docker node ls
   ```

5. **Inspect a Node**:
   ```bash
   docker node inspect <NODE-ID>
   ```

6. **Promote a Node to Manager**:
   ```bash
   docker node promote <NODE-ID>
   ```

7. **Demote a Manager Node to Worker**:
   ```bash
   docker node demote <NODE-ID>
   ```

8. **Remove a Node**:
   ```bash
   docker node rm <NODE-ID>
   ```

### Services
9. **Create a Service**:
   ```bash
   docker service create --name <SERVICE-NAME> <IMAGE>
   ```

10. **Scale a Service**:
    ```bash
    docker service scale <SERVICE-NAME>=<REPLICAS>
    ```

11. **List Services**:
    ```bash
    docker service ls
    ```

12. **Inspect a Service**:
    ```bash
    docker service inspect <SERVICE-NAME>
    ```

13. **Update a Service**:
    ```bash
    docker service update <SERVICE-NAME> --image <NEW-IMAGE>
    ```

14. **Remove a Service**:
    ```bash
    docker service rm <SERVICE-NAME>
    ```

### Stacks
15. **Deploy a Stack from Compose File**:
    ```bash
    docker stack deploy -c <COMPOSE-FILE> <STACK-NAME>
    ```

16. **List Stacks**:
    ```bash
    docker stack ls
    ```

17. **Inspect a Stack**:
    ```bash
    docker stack inspect <STACK-NAME>
    ```

18. **Remove a Stack**:
    ```bash
    docker stack rm <STACK-NAME>
    ```

### Secrets
19. **Create a Secret**:
    ```bash
    echo "<SECRET-DATA>" | docker secret create <SECRET-NAME> -
    ```

20. **List Secrets**:
    ```bash
    docker secret ls
    ```

### Configuration
21. **Create a Configuration**:
    ```bash
    docker config create <CONFIG-NAME> <CONFIG-FILE>
    ```

22. **List Configurations**:
    ```bash
    docker config ls
    ```

### Visualizer (Optional)
23. **Run Docker Swarm Visualizer**:
    Visualizer provides a graphical representation of your Swarm.
    ```bash
    docker run -it -d -p 8080:8080 -v /var/run/docker.sock:/var/run/docker.sock dockersamples/visualizer
    ```

