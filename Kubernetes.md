
# Setup

Ver comando de join de nodos 
* kubeadm token create --print-join-command

# Administración
kubectl codron NODE

Ver eventos de manera constante
Kubectl get events -w

### kubelet
sudo systemct restart kubelet

### Kubectl describe
kubectl describe node node01

## Pods

### Iniciar un pod por línea de comando

Iniciar nginx pod
* kubectl run nginx --image=nginx --port=80 --labels="app=nginx,env=prod"

### Gestión de pods

Para ver todos los pods
* kubectl get pod -A -o wide

Ver contenedores de namespace system con ip
* kubectl get pod -n kube-system -o wide

Para iniciar un contenedor de debug de networking https://hub.docker.com/r/nicolaka/netshoot
* kubectl run tmp-shell --rm -i --tty --image nicolaka/netshoot -- /bin/bash

## Deployments

Crear deployment desde command line
* kubectl create deployment hello-world --image=gcr.io/google-samples/hello-app:1.0

Escalar deployment
* kubectl scale --replicas=4 deployment/hello-world

## Services

Crear un servicio desde command line. Si no se especifica el --type, por defecto se usa ClusterIP
* kubectl expose deployment hello-world --port=8080 --target-port=8080 --type=ClusterIP

Crear un servicio tipo NodePort, este por defecto es accesible desde las ips de los nodos en puertos 30001 en adelante.
* kubectl expose deployment hello-world --port=8080 --target-port=8080 --type=NodePort

Crear servicio en infraestructura cloud usando load balancer
* kubectl expose deployment hello-world --port=8080 --target-port=8080 --type=LoadBalancer

## Ingress

helm list

Para remover un Helm chart de deployment:

helm delete <release-name>--purge

# Networking

Para ver adaptadores virtuales - virtual ethernets
* sudo ip link show type veth
* sudo ip link show type ipip (Calico usa ipip)

Para ver los bridges
* ip link show type bridge
* ip link show br0

## Networking flanel

Capturar tráfico entre pods por medio de vxlan
* tshark -V --color -i eth0 -d udp.port=8472,vxlan -f "port 8472"
* tshark -i eth0 -V -Y "http"

## Iptables
Para ver las reglas,"-n": sin resolver, "-t nat": de tipo nat, "-L": listando una chain
* sudo iptables -n -t nat -L KUBE-SERVICES
* sudo iptables -n -t nat -L KUBE-SVC-V2OKYYMBY3REGZOG

Las chains con SVC, ejempo: KUBE-SVC-* significa SerViCe
Las chains con SEP, ejempo: KUBE-SEP-* significa Service End Point

## CoreDNS

### Estructura de espacio de nombres

Nombre DNS de un servicio en el namespace default:
* app.default.svc.cluster.local

## DNS
Debug dns: https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/

