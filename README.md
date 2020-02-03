# kernelci-grafana

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
Default login and password: `admin / admin`

### Configure the datasource
Once your container started, go to http://your-container-url:3000/datasources/edit/1/ and add your account key.  
You might need to reset the current one to be able to add yours.  

### Configure the organisation
Go to http://your-container-url:3000/admin/orgs and add a new organisation `kernelci`
