### Deploy  kustomization.yaml 

kubectl apply -k .

kubectl exec -it mongo-0 -- mongo

rs.initiate()

 var cfg = rs.config()

 cfg.members[0].host="mongo-0:27017"

 rs.reconfig(cfg)

  rs.status()

  rs.add("mongo-1:27017")
  rs.add("mongo-2:27017")

### test

kubectl run mongo --rm -it --image mongo:4.2.23 sh

mongo mongodb://mongo-0:27017,mongo-1:27017,mongo-2:27017


mongo mongodb://mongo-0:27017,mongo-1:27017,mongo-2:27017/admin?replicaSet=rs0

mongo mongodb://cm9vdA==:ZXhhbXBsZQ==@mongo-0:27017,mongo-1:27017,mongo-2:27017/admin?replicaSet=rs0

mongo mongodb://mongo-0:27017,mongo-1:27017,mongo-2:27017 --eval 'rs.status()' | grep name

mongo mongodb://cm9vdA==:ZXhhbXBsZQ==@mongo-0.mongo-0:27017,mongo-1.mongo-1:27017,mongo-2.mongo-2:27017

mongo mongodb://mongo-0.mongo-0:27017,mongo-1.mongo-1:27017,mongo-2.mongo-2:27017/admin?replicaSet=rs0

mongo mongodb://192.168.137.129:32017,192.168.137.129:32018,192.168.137.129:32019


mongo mongodb://192.168.137.129:32017,192.168.137.129:32018,192.168.137.129:32019/admin?replicaSet=rs0



mongo mongodb://cm9vdA==:ZXhhbXBsZQ==@192.168.137.129:32017,192.168.137.129:32018,192.168.137.129:32019/admin?replicaSet=rs0



mongo mongodb://10.244.1.2:32017,10.244.2.2:32018,10.244.3.2:32019/admin?replicaSet=rs0
