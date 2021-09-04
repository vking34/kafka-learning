# Controller

- The controller is __one of the Kafka brokers__ that, in addition to the usual broker functionality, is __responsible for electing partition leaders__

- The __first broker__ that starts in the cluster becomes the controller by creating an ephemeral node in __ZooKeeper called /controller__