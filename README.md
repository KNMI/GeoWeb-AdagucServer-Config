# GeoWeb-AdagucServer-Config

Adaguc-server configuration files for GeoWeb

# Update all datasets:

```
dockercontainerid=`docker ps -f ancestor=adaguc-server -q`
docker exec -i -t ${dockercontainerid} /adaguc/adaguc-server-updatedatasets.sh
```

# Update a specific dataset:

```
dockercontainerid=`docker ps -f ancestor=adaguc-server -q`
filename=/data/adaguc-datasets/HARM_N25_ML.xml
 docker exec -t  ${dockercontainerid} bash -c "export ADAGUC_PATH=/adaguc/adaguc-server-master/ && export ADAGUC_TMP=/tmp && /adaguc/adaguc-server-master/bin/adagucserver --updatedb --config /adaguc/adaguc-server-config.xml,${filename}" 
```

# Dataset as service:
http://<yourhost>/adaguc-services/wms?dataset=HARM_N25_ML&
