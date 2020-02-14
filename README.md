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
Once your container started, go to http://your-container-url:3000/datasources/ and create a new datasource.
Choose BigQuery and add your json key file.


### Import dashboards
Go to http://your-container-url:3000/dashboards and click on `Import`
Copy the json file in `kernelci-grafana/dashboard/`.  
Select the Google BigQuery datasource and import.
Repeat this step for every dashboard.  

### Export your dashboards
The export feature is accessed in the share window which you open by clicking the share button in the dashboard menu.  
Click the checkbox for sharing for external use and save the json file.


### Save/Restore your instance
#### Save
https://github.com/rocker-org/rocker/wiki/How-to-save-data
#### Restore
If your image is saved on dockerhub  
`docker pull username/imagename`  
If your image is saved on your machine with docker commit, just run the image with the new name used for docker commit
