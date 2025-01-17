# www - Auxiliary

## Description

This repository manages the deployment of **www-auxiliary** microservice, which serves various static files and redirections under 'www' subdomain. These resources are not part of the WordPress ecosystem, but must be located in the www subdomain.

**Note: No local Docker dev environment**
This project doesn't provide a local Docker dev environment.

## Manage the service or resources

### Prerequisites

* Be member of the Keybase team 'epfl_www'
* Be member of the EPFL group 'vra_p_svc0041'

### Add a new file or folder

```bash
oc cp <my_file_or_dir> $(oc get pods -l app=www-auxiliary -o jsonpath='{.items[0].metadata.name}'):/public/www-auxiliary/
```

### Add a new redirection

Create the redirection in the NGINX [config](ansible/templates/nginx.conf)

### Deploy

```bash
./ansible/wwwsible      # (--prod for production environment)
```
