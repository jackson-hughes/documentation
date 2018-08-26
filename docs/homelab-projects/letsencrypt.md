# Letsencrypt

Letsencrypt provide free SSL certificates. 

---

## Initial Ideas

I intially explored using Terraform to spin up an EC2 instance, run user-data to generate a certificate and then copy it locally. 

My initial expectation was that I would have to provide a Challenge-Response using a webserver (Apache, NGINX), thus the terraform, however I chose to instead use the AWS Route53 provider. 

This meant that I no longer required a publicly accessable EC2 instance. 

I then had a brief look at Dockerising the process so it would become one command and produce the output of the certificate. This was still not ideal as there would be a manual process of implementing the certificate output onto the services that used it. 

---

In the end - I ended up writing an [Ansible role](https://github.com/jhughes01/ansible-homelab/tree/master/roles/certbot) so that nodes could generate and install their own LE certificates as required. 