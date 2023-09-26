# SLURM monitoring & logging practice

This Ansible playbook installs Prometheus with node_exporter and EFK stack on Centos 7:

    - prometheus
    - node_exporter
    - fluent_bit
    - elasticsearch

Default values and variables are located in ```defaults``` and ```vars``` directories of each role.

## To run this playbook you need docker and docker-compose installed. To build image use
docker build . -t local/centos  
## And now run docker-compose
docker-compose up  

