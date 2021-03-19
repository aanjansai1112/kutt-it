# kutt-it
This repo contains the kutt kubernetes deployment.

KUTT:
Kutt is a modern URL shortener with support for custom domains. Shorten URLs, manage your links and view the click rate statistics. Some Features: - Free and open source. - Custom domain support. - Custom URLs for shortened links - Setting password for links.

Change the configurations values in the configmaps file.

  dbHost: <db_host>
  dbName: <db_name>
  dbPassword: <db_password>
  dbUser: <db_user>
  redisHost: <redis_host>
  redisPort: "<redis_port>"


command to execute:

kubectl apply -f kutt-svc.yml -f kutt-config.yml -f kutt-deploy.yml -n <namespace>

pod:
saishreeanjan_autonom8_com@bastion-01:~/kutt$ kubectl get pods -n staging |grep kutt
kutt-dev-5c5f4d5668-pznjw                       1/1     Running   0          149m

Deployment
saishreeanjan_autonom8_com@bastion-01:~/kutt$ kubectl get deploy -n staging |grep kutt
kutt-dev                       1/1     1            1           3h6m

service
saishreeanjan_autonom8_com@bastion-01:~/kutt$ kubectl get svc -n staging |grep kutt
kutt-dev                              LoadBalancer   **.**.**.**    **.**.**.**      80:30597/TCP                                                      3h7m

configmaps
saishreeanjan_autonom8_com@bastion-01:~/kutt$ kubectl get configmap -n staging |grep kutt
kutt-dev                              6      3h8m


