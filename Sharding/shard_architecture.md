```
    stateDiagram-v2
    [*] --> Application
    direction LR
    state Application
    state QueryRouter 
    {
   
   mongos 
   }
   Application --> QueryRouter : Read
   QueryRouter --> Application: Results
    state cfg: config 
    {
        
        cfg1 
        cfg2
        cfg3
        
   }
    QueryRouter --> config
    config --> QueryRouter
   state Shard1: rs_mongo1
    {
    shard1_mongo1
    shard1_mongo2
    shard1_mongo3
    }
    state Shard2: rs_mongo2
    {
    shard2_mongo1
    shard2_mongo2
    shard2_mongo3
    }
    
    state Shard3: rs_mongo3 
    {
     shard3_mongo1
    shard3_mongo2
    shard3_mongo3
    }

    
      QueryRouter --> rs_mongo1
    QueryRouter --> rs_mongo2
    QueryRouter --> rs_mongo3
    rs_mongo1 --> QueryRouter
    rs_mongo2 --> QueryRouter
    rs_mongo3 --> QueryRouter
```
