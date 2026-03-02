GCP VM Autoscaling Demo

Overview

This project demonstrates automated VM autoscaling using Google Cloud
Platform (GCP). The implementation uses a Managed Instance Group (MIG)
configured with CPU-based autoscaling.

Project ID: g25ai1016
Instance Template: g25ai1016-instance-template-basic1
Instance Group: g25ai1016-instance-group

------------------------------------------------------------------------

Project Objectives

-   Deploy scalable VM infrastructure on GCP
-   Configure CPU-based autoscaling (60% threshold)
-   Implement security measures (IAM + Firewall)
-   Validate autoscaling behavior under load

------------------------------------------------------------------------

Architecture

-   Cloud Provider: Google Cloud Platform (GCP)
-   Region: asia-south1 (Mumbai)
-   Zone: asia-south1-c
-   Instance Template: g25ai1016-instance-template-basic1
-   Instance Group: g25ai1016-instance-group
-   Machine Type: e2-micro
-   Operating System: Debian 11
-   Scaling Policy: CPU-based autoscaling (Min: 1, Max: 3, Target: 60%)
-   Network: Default VPC with HTTP firewall rule (TCP 80)
-   Security: IAM Viewer role implementing least privilege

------------------------------------------------------------------------

Implementation Steps

1.  Enabled Compute Engine API and verified billing configuration.
2.  Created Instance Template: g25ai1016-instance-template-basic1
3.  Created Managed Instance Group: g25ai1016-instance-group
4.  Enabled Autoscaling:
    -   Minimum instances: 1
    -   Maximum instances: 3
    -   CPU utilization target: 60%
5.  Configured Firewall Rule:
    -   Allowed TCP port 80 (HTTP)
6.  Assigned IAM Viewer role to demonstrate restricted access.
7.  Performed load testing using stress tool.

------------------------------------------------------------------------

Testing

Load testing was performed using the stress utility inside the VM:

Command used:

    stress --cpu 2 --timeout 300

Observed Results: - CPU utilization exceeded 60% threshold (observed
peak ~98%). - Autoscaler increased target size. - Additional instances
entered provisioning state. - Scale-down occurred automatically after
CPU usage normalized.

------------------------------------------------------------------------

Security Validation

-   HTTP access allowed via firewall rule (TCP 80).
-   SSH access governed by default VPC rule (TCP 22).
-   Viewer IAM role verified to prevent SSH and modification access.
-   Permission error observed for compute.instances.setMetadata,
    confirming least privilege enforcement.

------------------------------------------------------------------------

Repository Structure

-   README.md
-   startup-script.sh
-   autoscaling-configuration.txt
-   firewall-config.txt
-   iam-role-config.txt

------------------------------------------------------------------------

This project validates both elasticity and security implementation
within a cloud infrastructure environment.
