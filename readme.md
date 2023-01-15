# Initial K8S setup

### Steps to do right after K8S cluster creation
1. Install `traefik` as a revers proxy (and for load balancing) [[more info](https://doc.traefik.io/traefik/getting-started/install-traefik/)]
2. Install `cert-manager` for SSL certificates [[more info](https://www.vultr.com/docs/how-to-deploy-a-secure-nginx-website-on-vultr-kubernetes-engine/#Configuring_cert_manager_for_Traefik_Ingress)]
3. Create Docker secret for pulling images from private repositories [[more info](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/)]

### Docker setup
```
kubectl create secret docker-registry regcred --docker-server=https://index.docker.io/v1/ --docker-username=abduvokhid --docker-password=<your-pword> --docker-email=abduvohid1996@gmail.com
```
Don't forget to replace `<your-pword>` with DockerHub access token!

### Steps to deploy each application
1. Create Dockerfile in the application repository
2. Create secret resource for environment variables of the application
3. Create a domain and point A record to the server
4. Generate SSL certificate for a domain
