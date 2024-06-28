# clone files from repo
git clone https://github.com/devopsjourney1/helm-webapp


# Create the helmchart
```
helm create helm-start
```


# Follow along with the video
- Create the files per the video, copying and pasting from templates-original
- you can also use the files in the solution folder

# Install the first one
```
helm install dx-release helm-start/ --values helm-start/values.yaml
```

# Upgrade after templating
```
helm upgrade dx-release helm-start/ --values helm-start/values.yaml
```

# Accessing it
```
minikube tunnel
```

# Create dev/prod
```
k create namespace dev
k create namespace prod
helm install dx-release-dev helm-start/ --values helm-start/values.yaml -f helm-start/values-dev.yaml -n dev
helm install dx-release-prod helm-start/ --values helm-start/values.yaml -f helm-start/values-prod.yaml -n prod
helm ls --all-namespaces
```
