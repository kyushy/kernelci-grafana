# kernelci-grafana

### Configure the datasource
Change the `clientEmail` and `privateKey` in `kernelci-grafana/provisioning/datasources/all.yml`

### Build Docker image  
```
cd kernelci-grafana
docker build -t kernelci-grafana .
```

### Run the docker image
```
docker run \
  -d \
  -p 3000:3000 \
  --name=grafana \
  -e "GF_INSTALL_PLUGINS=doitintl-bigquery-datasource" \
  kernelci-grafana
```
