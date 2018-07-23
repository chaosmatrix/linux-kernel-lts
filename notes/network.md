# Network

### Socket Options
1. SO_REUSEPORT
    * Advantage:
        1. better balance: hash(server_addr, server_port, client_addr, client_port
    * Disadvantage 
        1. may increase latancy in some type of workload
            * load balancing don't one connection/request complete time
        2. decrease listening process may cause some connection drop

### Ports
1. ip_unprivileged_port_start
    * Requires kernel > 4.11
    ```
    ip_unprivileged_port_start - INTEGER
	    This is a per-namespace sysctl.  It defines the first
	    unprivileged port in the network namespace.  Privileged ports
	    require root or CAP_NET_BIND_SERVICE in order to bind to them.
	    To disable all privileged ports, set this to 0.  It may not
	    overlap with the ip_local_reserved_ports range.

    Default: 1024
    ```

2. ip_local_reserved_ports
    * Why:
        * specify the ports which are reserved for some applications
    * example
        * sysctl -n ip_local_reserved_ports="1024-2048,8080"

3. ip_local_port_range
    * Why:
        * defines the local port range that is used by TCP and UDP to choose the local port
        * extend if too many sockets/connections
    * Example:
        * sysctl -n ip_local_port_range="32768 61000"

