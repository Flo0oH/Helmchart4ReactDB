How to use the React app backend Helmchart

This Helm chart installs a simple React web app, a PostgreSQL database, and an NGINX Load Balancer on an AWS cluster.
Prerequisites

    A running Kubernetes cluster on AWS
    The helm CLI installed on your local machine
    The necessary permissions to deploy resources on AWS using Terraform

Installing the Chart

    Add the chart repository to Helm:

css

$ helm repo add [repo-name] [repo-url]

    Use the following command to install the chart:

css

$ helm install [release-name] [repo-name/chart-name]

    You can access the deployed React app by using the URL provided in the output of the helm install command.

Accessing the PostgreSQL database

The PostgreSQL database can be accessed using the following information:

    Host: [database-service-name].default.[cluster-name].svc.cluster.local
    Port: 5432
    User: [user-defined-in-values.yaml]
    Password: [password-defined-in-values.yaml]

Configuration

You can configure the chart by providing values in a values.yaml file or by using the --set flag while installing the chart.

A sample values.yaml file:

yaml

postgresql:
  enabled: true
  postgresUser: [user]
  postgresPassword: [password]

webApp:
  enabled: true

nginx:
  enabled: true

Outputs

The helm install command provides the following outputs:

    URL of the deployed React web app

Further Resources

    React
    PostgreSQL
    NGINX
    Terraform AWS Provider
    Kubernetes

Outputs.tf

bash

output "webAppURL" {
  value = "${kubernetes_service.webApp.load_balancer_ingress.0.hostname}"
}
