# Network

### Socket Options
1. SO_REUSEPORT
    * Advantage:
        1. better balance: hash(server_addr, server_port, client_addr, client_port
    * Disadvantage 
        1. may increase latancy in some type of workload
            * load balancing don't one connection/request complete time
        2. decrease listening process may cause some connection drop

