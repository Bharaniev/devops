# ISTIO DEPLOYMENT

Istio Installation

curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.6.6 sh -

cd istio-1.6.6

echo "export PATH=$PWD/bin:$PATH" >> ~/.bash_profile

# use "istioctl install" instead
istioctl install --set profile=demo
```

====

FullAdmin:~/environment $ kubectl get pods -n istio-system
NAME                                   READY   STATUS    RESTARTS   AGE
grafana-7f44674447-d65tb               1/1     Running   0          31h
istio-egressgateway-6f87696595-z4xpd   1/1     Running   0          31h
istio-ingressgateway-bf7dd6754-fs8cp   1/1     Running   0          31h
istio-tracing-8549b858b6-99bpt         1/1     Running   0          31h
istiod-56d479f8c7-p2tv7                1/1     Running   0          31h
kiali-655dd5cfdc-22nrb                 1/1     Running   0          31h
prometheus-56996df56b-d5fjr            2/2     Running   0          31h

=====

FullAdmin:~/environment $ kubectl get svc -n istio-system                                                                            
NAME                        TYPE           CLUSTER-IP       EXTERNAL-IP                                                                  PORT(S)                                                                      AGE
grafana                     ClusterIP      172.20.78.0      <none>                                                                       3000/TCP                                                                     31h
istio-egressgateway         ClusterIP      172.20.63.12     <none>                                                                       80/TCP,443/TCP,15443/TCP                                                     31h
istio-ingressgateway        LoadBalancer   172.20.128.88    acf22a8c12dd64d658cfe969b391232d-1474842663.eu-central-1.elb.amazonaws.com   15021:30467/TCP,80:31010/TCP,443:30431/TCP,31400:30976/TCP,15443:32309/TCP   31h
istiod                      ClusterIP      172.20.248.126   <none>                                                                       15010/TCP,15012/TCP,443/TCP,15014/TCP,853/TCP                                31h
jaeger-agent                ClusterIP      None             <none>                                                                       5775/UDP,6831/UDP,6832/UDP                                                   31h
jaeger-collector            ClusterIP      172.20.161.165   <none>                                                                       14267/TCP,14268/TCP,14250/TCP                                                31h
jaeger-collector-headless   ClusterIP      None             <none>                                                                       14250/TCP                                                                    31h
jaeger-query                ClusterIP      172.20.140.153   <none>                                                                       16686/TCP                                                                    31h
kiali                       ClusterIP      172.20.162.9     <none>                                                                       20001/TCP                                                                    31h
prometheus                  ClusterIP      172.20.109.142   <none>                                                                       9090/TCP                                                                     31h
tracing                     ClusterIP      172.20.29.19     <none>                                                                       80/TCP                                                                       31h
zipkin                      ClusterIP      172.20.95.180    <none>                                                                       9411/TCP                                                                     31h


kubectl create ns istio-demo
kubectl label namespace istio-demo istio-injection=enabled



