# faindev-cluster
Note need to helm delete istio gateway before doing a terraform destroy

```
no metrics server
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml


helm install base ./base -n istio-system
helm install istiod ./istiod -n istio-system -f ./Istio-Umbrella-Chart/values-istiod.yml --wait
helm install gateway ./gateway -n istio-system -f ./Istio-Umbrella-Chart/values-gateway.yml

rm hexmap/charts/pyhexmap-chart-0.0.1.tgz
helm dependency build ./hexmap/
helm install pyhexmap ./HexMap-Umbrella-Chart/hexmap -n gaming

curl -X POST "http://testing.faindev.com/hexmap/new-map/7/6/4/5/5/"
```