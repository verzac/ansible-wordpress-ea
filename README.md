# ansible-wordpress-ea
This playbook is used by me to automate the deployment of a WordPress stack that I set up for a client.

## Prerequisites
* You need Ansible installed to run this playbook. Refer to (http://docs.ansible.com/ansible/latest/intro_installation.html) for more information on how to do this part.
* The playbook expects Ubuntu hosts. Other distros are currently not supported. That being said, you're more than welcome to try.

To run this playbook: `ansible-playbook -i hosts site.yml -e "host_key_checking=False"`

## Feature
* Automatic SSL/HTTPS configuration; certificate is obtained through Let's Encrypt (https://letsencrypt.org/) using the Webroot verification method
* Data persistence (for as long as you do not delete the volume defined in the Dockerfile)

## WordPress Stack Explanation
The WordPress stack is built using Docker. To accomplish this, the stack uses two Docker services (and, by extension, images): 'wordpress' and 'mysql'. These two images form a complete local stack, while the base NGINX acts as a proxy for the wordpress container.

## Additional Notes
> Q: Will you be supporting this?  
> A: Not really. I'm not planning to support this repository after I am done with my project. It's not meant for outside usage, and is only provided as an example for other people who want to learn how to use Ansible or Dockerized WordPress in a production environment.  

> Q: This thing is ugly and not scalable! Why?  
> A: I'm quite new to Ansible and Dockerized WordPress, so my playbook(s) may not follow best practices. In such cases, please feel free to shoot me a message, since I am keen on learning more!  
