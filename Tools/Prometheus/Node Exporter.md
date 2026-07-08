**Node Exporter** is an official, open-source Prometheus exporter designed to measure and expose host-level hardware and operating system metrics.

It runs as a background service (daemon) on Linux and other Unix-like systems, gathering system statistics and exposing them over an HTTP endpoint (usually port `9100`) in a plain-text format that Prometheus can readily scrape.

### Why Do We Need It?

Prometheus cannot look inside a server's operating system natively; it only knows how to scrape HTTP endpoints that speak its specific metric format.

Node Exporter acts as the **bridge between the OS kernel and Prometheus**. We need it to monitor the baseline health of bare-metal servers, virtual machines (VMs), or cloud instances (like AWS EC2).

#### 1. Core Hardware & OS Observability

Without it, you are blind to the host machine's actual performance. Node Exporter tracks critical system metrics, known as collectors, including:

- **CPU usage:** User time, system time, idle time, and iowait.
    
- **Memory usage:** Free, used, buffered, and cached RAM.
    
- **Disk I/O:** Read/write times, IOPS, and available disk space/inodes.
    
- **Network traffic:** Bytes sent/received, dropped packets, and errors on network interfaces.
    
- **System load:** 1-minute, 5-minute, and 15-minute load averages.
    

#### 2. Proactive Alerting & Capacity Planning

By gathering these metrics via Node Exporter, you can set up Prometheus alerts to catch infrastructure issues before they cause downtime:

- _Alert if disk space utilization is greater than 90%._
    
- _Alert if memory usage spikes and threatens to trigger the Linux OOM (Out of Memory) Killer._
    

#### 3. Root Cause Isolation

When an application slows down or crashes, Node Exporter metrics help you determine if it's an application bug or an underlying infrastructure bottleneck (e.g., high disk I/O wait times stalling your database).

### Quick Summary 

> "Node Exporter is a lightweight agent that runs on Linux hosts to collect hardware and OS-level metrics like CPU, memory, disk, and network usage. We need it because Prometheus cannot monitor host resources directly; Node Exporter surfaces these low-level system metrics over an HTTP endpoint so Prometheus can scrape and track the server's health."

