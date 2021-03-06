# SandBox: Play with Kong and Kubernetes APIs

## Goal

We have two operators which have some differences for their APIs, e.g. the API Group is different. We want to leverage Kong and Kong ingress controller to make the data transformation at server side to mitigate these difference so that client does not to change their calls made to Kubernetes even the operator behind is changed.


## Scenario

There are two operators: app1-operator vs. app2-operator, having different API groups, cache.example.com vs. cache2.example.com. Both will be deployed in kind along with Kong operator.

Deploy app1-operator first, then have client make the call to create a customer resource: Memcached, using API group cache.example.com.

Uninstall app1-operator, and install app2-operator, then have client make the same call using the same API group. It will still work even the operator at backend has been changed to use different API group.

![](docs/architecture.png)

## Tasks

* [x] [Prepare env](docs/tasks/01-prepare-env.md)
* [x] [Explore Kubernetes API](docs/tasks/02-explorer-k8s-api.md)
* [x] [Explore Kubernetes Authentication](docs/tasks/03-explorer-k8s-auth.md)
* [x] [Deploy sample operator](docs/tasks/04-deploy-sample-operator.md)
* [x] [Deploy two sample controllers with different API groups](docs/tasks/05-deploy-sample-controllers.md)
* [x] [Deploy Kong operator](docs/tasks/06-deploy-kong-operator.md)
* [x] [Enable TLS re-encryption for Kong](docs/tasks/07-enable-tls-with-kong.md)
* [x] [Understand what kubectl does behind](docs/tasks/08-understand-what-kubectl-does.md)
* [x] [URL rewriting using Kong](docs/tasks/09-url-rewriting-using-kong.md)
* [ ] Enable TLS passthrough for Kong (WIP)
* [ ] Enable TLS termination for Kong
* [ ] Call Kubernetes API via Kong inside cluster (WIP)
* [ ] Run kubectl to apply custom resource using Kong (WIP)
* [ ] Enable logging for Kong
* [ ] Enable metrics for Kong
* [ ] Put all things together
