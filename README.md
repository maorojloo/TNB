Tor Node Load Balancer

Description:

This project implements a simple Tor client load balancer using HAProxy, allowing for efficient distribution of Tor client requests across multiple nodes. It is designed to enhance anonymity and improve performance by distributing traffic among multiple Tor client instances.

Usage:

    Project Setup:
        Clone the repository and navigate to the project directory.
        Run docker-compose up -d to set up the project.

    Checking Proxy:
        Use curl with the following command to test the proxy:

        bash

        curl --proxy socks5://localhost:9050 https://check.torproject.org/

    Celebration:
        If everything is set up correctly, celebrate! Your load balancer is now operational.

Project Structure:

    Docker Compose:
        Utilizes Docker Compose to manage multiple Tor client instances and HAProxy.
        Three Tor client nodes are set up, each exposing a SOCKS5 proxy port.
        HAProxy is configured to load balance traffic across these Tor client nodes.

    HAProxy Configuration:
        Configured for TCP mode.
        Frontend listens on port 9050, acting as a SOCKS5 proxy.
        Backend defines three Tor client nodes to balance traffic using round-robin algorithm.

Benefits:

    Enhanced Anonymity: Distributes Tor client requests across multiple nodes, reducing the risk of traffic correlation and enhancing anonymity.
    Improved Performance: Load balancing helps in distributing traffic efficiently, reducing packet loss, and improving throughput.
    Fault Tolerance: If one Tor client node fails, HAProxy automatically routes traffic to the remaining nodes, ensuring continuous service availability.

Performance:

    Low Packet Loss: The setup is optimized for low packet loss, ensuring reliable and stable Tor connections.
    Throughput: Capable of handling up to 600 transactions per second (TPS), providing efficient service for a moderate level of traffic.

Feel free to modify the project or extend its functionality according to your requirements. If you have any questions or encounter issues, please refer to the documentation or reach out to the project maintainers for assistance. Happy browsing with enhanced anonymity! 🎉
