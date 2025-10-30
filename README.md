# Elevatelab-task07

The objective of this task was to install and configure Netdata, an open-source real-time monitoring tool, to visualize and analyze system performance metrics such as CPU usage, memory utilization, disk activity, and Docker container statistics. The task was performed using Docker on an Ubuntu (WSL2) environment.

To begin, the Netdata container image was pulled and run using the command sudo docker run -d --name=netdata -p 19999:19999 netdata/netdata. This command launched Netdata in detached mode while exposing port 19999 for web access. After the container was started, its status was verified using sudo docker ps. If the container was not running, it could be started manually with sudo docker start netdata.

Once the container was active, the Netdata dashboard became accessible via a web browser at http://localhost:19999. In the WSL2 environment, the dashboard could also be accessed using the system’s IP address. On the dashboard’s welcome screen, selecting “Skip and use the dashboard anonymously” provided access to the live system metrics.

Inside the Netdata dashboard, various system metrics were displayed in real time. The CPU section showed detailed usage per core, including user, system, and idle times. The memory section provided a live view of used, cached, and free memory. The disk monitoring section displayed read and write rates, as well as I/O utilization. Additionally, Netdata automatically detected and monitored Docker containers, presenting each container’s CPU, memory, and network usage.

During this task, several issues were encountered and resolved. For example, if port 19999 was already in use, it caused a container startup error. This was resolved by removing the old container using sudo docker rm -f netdata before running a new one. In cases where the dashboard was inaccessible from the browser, retrieving the IP address with hostname -I allowed successful access through the correct URL. These troubleshooting steps helped in understanding container management and network configuration better.

Through this task, I learned how to deploy Netdata using Docker, access its dashboard, and monitor system and container-level metrics effectively. I also gained practical experience in diagnosing issues like port conflicts and container restarts. This exercise enhanced my understanding of real-time monitoring, performance visualization, and the importance of resource tracking in DevOps environments. Netdata proved to be a lightweight yet powerful monitoring solution for ensuring system health and stability.

The task concluded successfully with the Netdata dashboard displaying real-time charts for CPU performance, memory usage, disk I/O, and Docker container metrics, providing a comprehensive overview of system activity and resource utilization.
