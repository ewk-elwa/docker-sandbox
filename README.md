# docker-sandbox
Playing around with docker

## Steps to stand up the docke env and checkout the networks
```
docker-compose up
docker ps | grep special

echo "*************************************************"
echo "Demo route from PROXY to APP"
docker exec special-net-proxy-1 curl special-net-app-1

echo "*************************************************"
echo "Demo no route from PROXY to DB"
docker exec special-net-proxy-1 curl special-net-db-1


echo "*************************************************"
echo "Demo route from DB to APP"
docker exec special-net-db-1 curl special-net-app-1

echo "*************************************************"
echo "Demo no route from DB to PROXY"
docker exec special-net-db-1 curl special-net-proxy-1


echo "*************************************************"
echo "Demo route from APP can reach both DB and PROXY"
docker exec special-net-app-1 curl special-net-proxy-1
docker exec special-net-app-1 curl special-net-DB-1
```
