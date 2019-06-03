# aarch64-sawtooth
This page is Sawtooth for the aarch64 architecture.

Currently, only the Devmode consensus algorithm is supported.

Within the next week, we will create a Docker image that supports raft, poet and seth.

At that time, we will upload the corresponding Docker-compose.yaml file.


I have not made a client image yet.

I have linked REST-API with another image file.

You can use it as follows.


user@host$ docker-compose -f sawtooth-default.yaml up

user@host$ docker exec -it sawtooth-intkey-tp-python bash

root@sawtooth-intkey-tp-python#

root@sawtooth-intkey-tp-python# curl http://rest-api:8008/blocks

root@sawtooth-intkey-tp-python# intkey create_batch --count 10 --key-count 5
Writing to batches.intkey...

root@sawtooth-intkey-tp-python# intkey load -f batches.intkey --url http://rest-api:8008
batches: 11 batch/sec: 141.7800162868952


sudo docker-compose -f sawtooth-0000.yaml up
sudo docker-compose -f sawtooth-0000.yaml down -v

