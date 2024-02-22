# minikube-assignment

Kubernetes Deployment on Minikube with Nginx Ingress and TLS:

This guide walks through the process of setting up a Minikube Kubernetes cluster on an Azure Ubuntu VM, deploying an Nginx Ingress Controller, a sample "Hello World" application, and securing it with a self-signed TLS certificate.

Overview
The setup involves several key steps:

Minikube Setup:

Installation and configuration of Minikube on an Azure Ubuntu VM to create a local Kubernetes cluster.
Nginx Ingress Controller Deployment: Using Helm to install the Nginx Ingress Controller, allowing external access to services within the cluster.
"Hello World" Application Deployment: Creating and deploying a simple web application to demonstrate service exposure through the Ingress Controller.

TLS Implementation:

Generating a self-signed SSL certificate and applying it to the Ingress to secure traffic.

Prerequisites
An Azure account with an Ubuntu VM.
Minikube installed on the Ubuntu VM.
Helm installed for deploying the Nginx Ingress Controller.
Ansible installed for automation of deployment tasks.
Kubectl configured to interact with your Minikube cluster.
Detailed Steps
Minikube Configuration

Minikube Start: 
Initialize Minikube with minikube start, ensuring it's configured to allocate sufficient resources (CPU, memory) for your applications.
Deploying the Nginx Ingress Controller
Helm Installation: Use Helm to deploy the Nginx Ingress Controller into the kube-system namespace, enabling traffic management for applications deployed within Minikube.
Deploying the "Hello World" Application

Application Setup: Deploy a simple "Hello World" application using a Deployment and Service. This demonstrates how to expose applications within the cluster.
Ingress Configuration: Define an Ingress resource to route external requests to the "Hello World" service, showcasing domain-based access to internal services.
TLS Implementation
Certificate Generation: Utilize Ansible to generate a self-signed SSL certificate, highlighting how to secure communication to the cluster.
Secret Creation: Create a Kubernetes Secret to store the SSL certificate and key, demonstrating secure certificate management within Kubernetes.
Ingress 

TLS Setup: Update the Ingress resource to use the TLS secret for HTTPS traffic, ensuring encrypted communication to the "Hello World" application.
Network Configuration on Azure

NSG Rules: Configure Network Security Group (NSG) rules to allow inbound traffic on necessary ports (e.g., 80, 443, NodePort ranges) for external access to the services.

Firewall Settings: Adjust the VM's firewall settings (if any) to align with the NSG rules, ensuring seamless traffic flow to the Minikube cluster.
Accessing the Application

Verify external access to the "Hello World" application via the configured Ingress path, using the VM's public IP and ensuring HTTPS traffic is correctly encrypted.
