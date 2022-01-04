# ISTIO DEPLOYMENT

Istio Installation

curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.6.6 sh -

cd istio-1.6.6

echo "export PATH=$PWD/bin:$PATH" >> ~/.bash_profile

# use "istioctl install" instead
istioctl install --set profile=demo
```
![image](https://user-images.githubusercontent.com/94818369/148058651-66412358-4098-4e5b-8b41-b7beb668048a.png)

![image](https://user-images.githubusercontent.com/94818369/148058696-dcc6f0f8-e8ee-4a12-bd85-5833fd248e79.png)

