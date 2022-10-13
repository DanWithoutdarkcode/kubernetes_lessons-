### Deploy  kustomization.yaml 

kubectl apply -k .

kubcetl exec -it mongo-0 -- mongo

rs.initiate()

 var cfg = rs.config()

 cfg.members[0].host="mongo-0.mongo:27017"

 rs.reconfig(cfg)

  rs.status()

  rs.add("mongo-1.mongo:27017")
  rs.add("mongo-2.mongo:27017")

### test

kubectl run mongo --rm -it --image mongo:4.2.23 sh


mongo mongodb://mongo-0.mongo:27017,mongo-1.mongo:27017,mongo-2.mongo:27017/admin?replicaSet=rs0
